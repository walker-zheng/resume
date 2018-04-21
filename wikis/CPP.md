# C++11
### `std::async`
* **`std::async` is a neat and easy way to get a `std::future`, but:**

  * Not always it starts a new thread; pass `std::launch::async` as a first parameter to force it.
```
auto f = std::async( std::launch::async, func );
```
  * the `std::~future` destructor can block until new thread finishes
```
auto sleep = [](int s) { std::this_thread::sleep_for(std::chrono::seconds(s)); };
{
    auto f = std::async( std::launch::async, sleep, 5 );
}
```
  * Normally we expect that only .get() or .wait() blocks, but for `std::future` returned from `std::async` destructor also may block, so be careful not to block your main thread just by forgetting about it.
  * if the `std::future` is stored in a temporary-life object, `std::async` call will block on spot, so the following block will take 10 seconds if you remove the auto
```
f = initializations:
auto sleep = [](int s) { std::this_thread::sleep_for(std::chrono::seconds(s)); };
{
    auto f1 = std::async( std::launch::async, sleep, 5 );
    auto f2 = std::async( std::launch::async, sleep, 5 );
}
```

### `std::packaged_task`
* `std::packaged_task` by itself has nothing to do with threads: it is just a functor and a related future. Consider the following:

```
auto task = [](int i) { std::this_thread::sleep_for(std::chrono::seconds(5)); return i+100; };
std::packaged_task< int(int) > package{ task };
std::future<int> f = package.get_future();
package(1);
std::cout << f.get() << "\n";
```

Here we just run the task by package(1), and after it returns f is ready so no blocking on .get().

But: one feature make the packaged_task very useful for threads. Instead of just a function you can initialize std::thread with a packaged_task. Consider the following - packaged_task is a really nice way of getting future:

```
std::packaged_task< int(int) > package{ task };
std::future<int> f = package.get_future();
std::thread t { std::move(package), 5 };

std::cout << f.get() << "\n";       //block here until t finishes

t.join();
```
* `std::packaged_task` is not copyable, so you move it to new task with `std::move`.

### `std::promise`
* `std::promise` is a powerful mechanism, for example you can pass a value to new thread without need of any additional synchronizing mechanism.

```
auto task = [](std::future<int> i) {
    std::cout << i.get() << std::flush;
};

std::promise<int> p;
std::thread t{ task, p.get_future() };

std::this_thread::sleep_for(std::chrono::seconds(5));
p.set_value(5);

t.join();
```
New thread will wait for us on .get()

### So, in general, answering your question:

* use `std::async` only for simple things, e.g. to make some call non-blocking, but bear in mind the comments on blocking above.
* use `std::packaged_task` to easily get future, and run it as a separate thread

```
std::thread{ std::move(package), param }.detach();
```
or

```
std::thread t { std::move(package), param };
```
* use `std::promise` when you need more control over the future.

### `std::packaged_task`使用
* Firstly, if you declare std::packaged_task to take arguments, then you must pass them to operator(), not the constructor. In a single thread you can thus do:
```
std::packaged_task<int(int,int)> task(&ackermann);
auto f=task.get_future();
task(3,11);
std::cout<<f.get()<<std::endl;
```
* To do the same with a thread, you must move the task into the thread, and pass the arguments too:
```
std::packaged_task<int(int,int)> task(&ackermann);
auto f=task.get_future();
std::thread t(std::move(task),3,11);
t.join();
std::cout<<f.get()<<std::endl;
```
* Alternatively, you can bind the arguments directly before you construct the task, in which case the task itself now has a signature that takes no arguments:
```
std::packaged_task<int()> task(std::bind(&ackermann,3,11));
auto f=task.get_future();
task();
std::cout<<f.get()<<std::endl;
```
* Again, you can do this and pass it to a thread:
```
std::packaged_task<int()> task(std::bind(&ackermann,3,11));
auto f=task.get_future();
std::thread t(std::move(task));
t.join();
std::cout<<f.get()<<std::endl;
```
