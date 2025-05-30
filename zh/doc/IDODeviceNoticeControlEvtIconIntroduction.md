# {IDO设备通知/控制事件说明}

## 1.功能概述

提供监听手环/手表设备发送通知事件、控制事件、快捷短信和固件错误码到APP的能力。

## 2.接口能力

### 1.数据类型通知事件：

#### 1.1 功能概括:

数据类型通知事件说明。

#### 1.2 API ID:

````dart
final int? dataType;
````

#### 1.3 API参数说明:

| 十进制值 | 说明                                                         |      |
| -------- | ------------------------------------------------------------ | ---- |
| 0        | 无效                                                         |      |
| 1        | 手环已经解绑                                                 |      |
| 2        | 心率模式改变                                                 |      |
| 3        | 血氧产生数据，发生改变                                       |      |
| 4        | 压力产生数据，发生改变                                       |      |
| 5        | Alexa识别过程中退出                                          |      |
| 6        | 固件发起恢复出厂设置，通知app弹框提醒                        |      |
| 7        | app需要进入相机界面（TIT01定制）                             |      |
| 8        | sos事件通知（205土耳其定制）                                 |      |
| 9        | alexa设置的闹钟，固件修改，需要发送对应的通知位给app，app收到后发送获取V3的闹钟命令 |      |
| 10       | 固件有删除日程提醒，app这边需要更新对应的列表数据            |      |
| 11       | 固件端有修改对应的表盘子样式，通知app获取（command\_id为0x33， key为 0x5000） |      |
| 12       | 固件通知ios更新通知图标和名字                                |      |
| 13       | 固件通知app图标已经更新，通知app获取已经更新的图标状态       |      |
| 14       | 固件请求重新设置天气，app收到收，下发天气数据                |      |
| 15       | 步数每次增加2000步，设备请求app同步数据，app调用同步接口     |      |
| 16       | 探测到睡眠结束，请求app同步睡眠数据，app调用同步接口同步     |      |
| 17       | 固件三环数据修改，通知app更新三环数据                        |      |
| 18       | 固件充满电完成发送提醒，app收到后通知栏显示设备充电完成      |      |
| 19       | 结束运动后，手动测量心率后，手动测量血氧后，手动测量压力后，设备自动请求同步，先检查链接状态，未连接本次同步不执行，满足下个自动同步条件后再次判断发起同步请求 |      |
| 20       | 固件修改 心率通知状态类型、压力通知状态类型、血氧通知状态类型、生理周期通知状态类型、健康指导通知状态类型、提醒事项通知状态类型通知app更新心率、压力、血氧、生理周期、健康指导、提醒事项通知状态类型 |      |
| 21       | 固件压力值计算完成，通知app获取压力值                        |      |
| 22       | 固件通知app，固件压力校准失败(固件退出测量界面/检测失败/检测超时/未佩戴) |      |
| 23       | 保留                                                         |      |
| 24       | 固件通知app bt蓝牙已连接                                     |      |
| 25       | 固件通知app bt蓝牙断开连接                                   |      |
| 26       | 固件蓝牙通话开始                                             |      |
| 27       | 固件蓝牙通话结束                                             |      |
| 28       | 新版本固件每隔4分30秒发送一个通知命令用于修复ios 会显示离线的问题 |      |
| 29       | 通知app运动开始（作用于拦截表盘传输同26）                    |      |
| 30       | 通知app运动结束（作用于拦截表盘传输同27）                    |      |
| 31       | 固件重启发送通知给app  （app收到通知需要获取固件版本信息）   |      |
| 32       | 设备空闲时（没有使用aleax），需要上报通知给app（时间间隔为1小时） |      |
| 33       | 固件整理空间完成通知app继续下传表盘文件                      |      |
| 34       | 固件通知app结束寻找手环指令 （对应6.3寻找手环）              |      |
| 35       | 固件进入省电模式通知app                                      |      |
| 36       | 固件退出省电模式通知app                                      |      |
| ~~37~~   | ~~固件通知请求app下发设置gps热启动参数(废弃)~~               |      |
| 38       | 固件传输原始数据完成，通知app获取特性向量信息                |      |
| 39       | 固件通知app，固件血压校准失败(固件退出测量界面/检测失败/检测超时/未佩戴) |      |
| 40       | 固件传输原始数据完成，没有特性向量信息，通知app数据采集结束  |      |
| 41       | v3健康数据同步单项数据完成通知 (android 内部使用）           |      |
| 42       | 固件整理gps数据空间完成通知app下发gps文件                    |      |
| 43       | 固件升级EPO.dat文件失败，通知app再次下发一次该文件           |      |
| 44       | 固件升级EPO.dat文件成功                                      |      |
| 45       | 固件升级GPS失败，通知app重新传输                             |      |
| 46       | 固件升级GPS成功                                              |      |
| 47       | 发起运动时, 固件GPS异常，通知app                             |      |
| 48       | 固件润丰外设信息更新，通知app获取                            |      |
| 49       | 固件通知用户取消ble和手表配对,app弹窗处理                    |      |
| 50       | 固件通知app bt配对完成                                       |      |
| 51       | 固件设置运动排序,通知app获取运动排序信息                     |      |
| 52       | 固件全天步数目标参数有更改,通知app获取全天步数目标(0208)     |      |
| 53       | 固件通知app固件进入血压校准界面                              |      |
| 54       | 固件自动识别开关状态更新,通知app获取运动自动识别开关状态(02EA) |      |



### 2.消息类型通知事件：

#### 2.1 功能概括:

消息类型通知事件说明。

#### 2.2 API ID:

````dart
final int? notifyType;
````

#### 2.3 API参数说明:

| 十进制值 | 说明             |
| -------- | ---------------- |
| 1        | 闹钟已经修改     |
| 2        | 固件过热异常告警 |
| 4        | 亮屏参数有修改   |
| 8        | 抬腕参数有修改   |
| 16       | 勿擾模式获取     |
| 32       | 手机音量的下发   |



### 3.消息ID：

#### 3.1 功能概括:

无。

#### 3.2 API ID:

````dart
final int? msgId;
````

#### 3.3 API参数说明:

@param:每个消息对应一个ID



### 4.快捷短信通知：

#### 4.1 功能概括:

无。////TODO快捷短信如何设置

#### 4.2 API ID:

````dart
final int? msgNotice;
````

#### 4.3 API参数说明:

| 值   | 说明                            |
| ---- | ------------------------------- |
| 0    | 无                              |
| 1    | 自定义短信1(正在开会，稍后联系) |
| 2    | 自定义短信2                     |
| 3    | 自定义短信3                     |
| 4    | 自定义短信4                     |
| 5    | 自定义短信5                     |
| ..   | ..(依次类推到10)                |
| 10   | 自定义短信10                    |



### 5.固件错误码通知：

#### 5.1 功能概括:

监听到固件的错误码通知，APP获取固件Flash日志。

#### 5.2 API ID:

````dart
final int? errorIndex;
````

#### 5.3 API参数说明:

| 值   | 错误类型     |
| ---- | ------------ |
| 0    | 没有错误     |
| 1    | ACC          |
| 2    | PPG          |
| 3    | TP           |
| 4    | FLASH        |
| 5    | 过热（PPG）  |
| 6    | 气压         |
| 7    | GPS          |
| 8    | 地磁         |
| 100  | 开门狗复位   |
| 101  | 上电复位     |
| 102  | 软件错位复位 |
| 103  | OTA复位      |
| 104  | 用户主动复位 |
| 105  | 低电关机复位 |

备注:1~100是固件错误码，100~200复位日志码。



### 6.控制事件通知：

#### 6.1 功能概括:

无。

#### 6.2 API ID:

````dart
final int? controlEvt;
````

#### 6.3 API参数说明:

| 控制事件                  | 事件号 |
|-----------------------| ------ |
| 设备控制app音乐开始           | 551    |
| 设备控制app音乐暂停           | 552    |
| 设备控制app音乐停止           | 553    |
| 设备控制app音乐上一首          | 554    |
| 设备控制app音乐下一首          | 555    |
| 设备控制app拍照单拍           | 556    |
| 设备控制app拍照连拍           | 557    |
| 设备控制app音量加            | 558    |
| 设备控制app音量减            | 559    |
| 设备控制app打开相机           | 560    |
| 设备控制app关闭相机           | 561    |
| 设备控制app接听电话           | 562    |
| 设备控制app拒接电话           | 563    |
| 设备控制app音乐音量百分比        | 565    |
| 设备控制打开APP相机，进入相机预览功能  | 567                | 
| 设备控制暂停相机预览，停止传输照片流    | 568                | 
| 设备控制关闭APP相机，退出相机预览功能  | 569                | 
| 设备控制app寻找手机开始         | 570    |
| 设备控制app寻找手机结束         | 572    |
| 设备通知app防丢启动           | 574    |
| 设备通知app一键呼叫开始         | 575    |
| 设备通知传感器数据 设备通知app操作类型 | 576    |
| 设备通知app数据更新           | 577    |
| 设备请求版本检查              | 578    |
| 设备请求ota               | 579    |
| 设备通知app短信信息           | 580    |
| 设备控制app相机             | 581    |
| 设备通知固件喇叭音量修改          | 591    |



### 7.控制事件返回参数：

#### 7.1 功能概括:

无。

#### 7.2 API ID:

````dart
final String? controlJson;
````

#### 7.3 API参数说明:

事件号说明和对应事件项内容说明跳转到 => [设备主动通知/控制事件](BaseProtocolEvtExecDoc/IDODeviceControlEvt/IDODeviceControlEvtIntroduction.md) ////TODO有控制事件没有参数 优化



