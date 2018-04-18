# **郑美洋**

## C++软件开发工程师

* [简介](#简介)
* [个人资料](#个人资料)
* [专业技能](#专业技能)
* [工作经历](#工作经历)
* [项目经验](#项目经验)

## 简介

喜欢有挑战的工作和生产力技术，良好的沟通能力，扎实的编程功底和编程经验，优秀的学习和分析解决问题的能力，能独立完成复杂的高性能软件。

超过七年软件开发经验，熟悉C/C++语言，熟悉高性能网络并发，Poco库等；熟练掌握shell，熟悉Git开发管理及redis使用等；了解grpc/json-rpc/rest等技术，了解微服务设计等；

## 个人资料

* 姓名: `郑美洋`
* 邮箱: [`mykulou@gmail.com`](mykulou@gmail.com)
* 电话: `185 1614 7671`
* 专业: `西南交大-计算机(2006-2010)`
* 学历: `本科`

## 专业技能

* C++高性能服务器开发
* Git项目管理（git-flow/github工作流，gogs团队管理）
* Shell脚本开发，自动化和文本处理
* 跨平台GUI程序开发（electron&grpc/json-rpc&c++）
* 持续集成和开发管理
* 数据可视化展示技术
* 了解TCP/IP
* 性能分析和优化

## 工作经历

### 杰勤信息技术\|c++研发工程师 `[2015/12-2017/11]`

* 工作描述：

  开发任务调度服务器，为算法服务器产生任务，为内控中心实现不同风险规则的实时/定时任务等的定制和报警上传、信息汇总等；  
  开发GUI管理工具，管理数据库备份/恢复，软件包升级等；

  编写shell脚本便于日志分析和自动化处理等；

  管理Git服务器，采用git-flow工作流和gogs管理团队项目开发；

### 上海广拓信息技术\|c++研发工程师 `[2014/07-2015/12]`

* 工作描述：

  开发及维护包括网络摄像头\(IPC\)/网络硬盘录像机\(NVR\)/解码器等的SDK，并打包成OCX嵌入IE页面，方便通过web直接管理硬件设备和观看视频；

  开发多个与嵌入式设备\(多种电子围栏键盘和报警主机\)通讯的SDK，并提供GUI管理工具，集成多种设备的管理功能等；

  安防视频管理平台中，负责各厂商SDK集成和对接，兼容不同厂商设备管理控制功能，保证不同厂商的录像和视频流的都可以正常点播和播放；

### 江苏视图信息技术\|算法工程师 `[2013/07-2014/03]`

* 工作描述：

  图像处理算法设计和编码及脚本开发，图像搜索匹配算法优化和调优等；

### 软通动力\|中级软件工程师 `[2010/07-2013/09]`

* 工作描述：

  IPTV产品线下属子系统MDN的开发，编写工具模拟测试点播/直播流程的通讯，分析视频码流是否正常，保障系统稳定性；  
  ISMP平台核心模块MDCC鉴权计费的维护和业务需求开发。

## 项目经验

### 任务管理调度服务器 `[2015/12-2017/11]`

* 软件环境：windows/vs2015
* 责任描述：

  开发任务管理调度服务器，从结构设计、接口设计、性能优化、打包发布、批量模拟测试、脚本日志分析，业务流程分析和实现，实现简单的任务管理等功能，根据需求修改任务生成逻辑，增加新的功能等；

* 项目简介：

  任务管理调度服务器，根据内控中心的配置，用不同风险点检查规则对不同业务或时段的视频生产的实时/历史视频分析任务，将任务交给算法分析服务器，并将报警结果反馈给内控中心；实时上报任务状态和任务统计等信息，可管理任务的启动/暂停/继续/停止等；

### 安防报警平台 `[2015/04-2015/12]`

* 软件环境：windows/vs2010
* 责任描述：

  报警模块SDK接入，各厂商摄像头/网络硬盘录像机的SDK的接入和兼容，各厂商的视频流/录像的兼容解码和播放；

* 项目简介：

  防报警平台支持接入和管理不同厂商的IPC/NVR设备的SDK，并集成本公司围栏和报警主机等报警设备SDK，可以直接管理配置；平台兼容主流厂商的软硬件设备，实现解码播放存储及配置管理等的统一化；

### PC端SDK及管理工具开发 `[2014/07-2015/04]`

* 软件环境：windows/vs2010

* 责任描述：  
  开发SDK与嵌入式设备通讯，实现管理功能，集成和兼容多种设备的SDK，同时管理多种设备\(不同型号围栏键盘、各类报警主机等\)，开发相关图形化设备管理工具；

  开发视频解码器的SDK，打包成OCX，供IE调用，在web页面实现设备的控制管理功能，可播放视频流和录像；

  开发及维护IPC/NVR等的SDK;

* 项目简介：

  键盘可以管理多个防区的电子围栏设备，是围栏的配套设备，可手动设置布撤防等功能；报警主机可以报警，显示某段围栏有入侵或异常等；SDK可通过网络对键盘、报警主机进行统一管理，并兼容不同型号设备，能通过管理大规模的不同安防设备；  
  IPC/NVR/解码器等设备的SDK，可以打包成OCX可方便IE调用，直接通过web页面管理设备，不需安装管理软件，更方便快捷；

### 图像处理和SIFT图片搜索优化 `[2013/07-2014/03]`

* 软件环境：windows/linux/vs2010
* 责任描述：

  负责开发图像处理工具和自动脚本，自动处理和产生不同需求图片，提高图片识别质量并保证效率。  
  参与SIFT算法优化，使用轮廓识别主体，提高图片匹配率

* 项目简介：

  对图片进行去噪去背景去logo等处理，用轮廓识别主体，以提高SIFT算法图像匹配率；批量处理转换成不同尺寸的图片，以适应各种需求；使用轮廓和中心范围阈值优化SIFT匹配等；代码跨平台编译等。基于opencv视觉库开发，运行于多个平台\(linux/cygwin/win\)。

### ISMP电信业务平台鉴权模块MDCC的需求开发 `[2012/09-2013/07]`

* 软件环境：sourceinsight vs2010 pclint

* 责任描述：

  负责ISMP综合业务管理平台的鉴权计费模块MDCC的需求开发，对产品发布、订购等做鉴权和话单计费；保证系统稳定运行，为系统稳定性分析和业务分析提供日志和记录；扩展对外接口，增强手机付费能力；增量需求开发，以应对不同局点业务变化。

* 项目简介：

  MDCC是移动数据业务管理平台，是ISMP综合业务管理平台的鉴权计费系统，有多个局点使用，对产品发布、订购等做鉴权和话单计费等业务进行管理；为系统稳定运行和业务日志分析，增加日志入库和告警功能；对外接口改造以兼容IPTV、VNET，提供更多付费内容。

#### MDN媒体服务器稳定性检测 `[2010/07-2012/09]`

* 软件环境：linux vim

* 责任描述：

  检查分析流媒体服务器发送音视频流的关键信息，码流分析，确保工作正常；  
  提供稳定的消息模拟部件，通过直播/点播等流程，对MDN各模块及外部系统进行消息交互测试等；

* 项目简介：

  IPTV下属子系统媒体分发网MDN的工具开发。检测MDN传送的音视频流是否连续、是否存在丢帧和重复情况、CC及GOP等关键数据是否符合预期，以确保流服务器正常工作。编写测试工具和脚本模拟真实部件，收发消息和音视频流并校验，以提供灵活的测试部件。



