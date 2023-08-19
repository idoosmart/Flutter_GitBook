# {IDO基础事件字段说明}

### 1.功能概述

**基础事件流程：**APP下发基础事件通过Flutter接口**`libManager.send(evt,json)`**，将事件号和对应事件号的事件项通过C库组包成字节数据，再有蓝牙库将字节数据发送到设备，等待设备回应字节数据后，蓝牙库通过Flutter接口**`receiveDataFromBle(data,macaddress,type)`**解析字节数据，最终APP的到的Json格式的回应内容，实现APP与设备的交互。

为了帮助APP开发，这个入口介绍基础事件的事件号和事件项内容。



### 2.基础事件

| **[V2设置指令事件](zh/doc/IDOV2SetEvt/IDOSetEvtIntroduction.md)** |
| :----------------------------------------------------------- |
| **[V2获取指令事件](zh/doc/IDOV2GetEvt/IDOGetEvtIntroduction.md)** |
| **[V3长包指令事件](zh/doc/IDOV3Evt/IDOV3EvtIntroduction.md)** |
| **[OTA指令事件](zh/doc/IDOOtaEvt/IDOOtaEvtIntroduction.md)** |
| **[APP发起通知/控制事件](zh/doc/IDOControlEvt/IDOControlEvtIntroduction.md)** |
| **[设备主动通知/控制事件](zh/doc/IDODeviceControlEvt/IDODeviceControlEvtIntroduction.md)** |
| **[运动数据交互事件(内部使用)](zh/doc/IDOSportSwitchEvt/IDOSportSwitchEvtIntroduction.md)** |
| **[同步V3健康数据事件(内部使用)](zh/doc/IDOV3HealthSyncEvt/IDOV3HealthSyncEvtIntroduction.md)** |
| **[Alexa事件(内部使用)](zh/doc/IDOAlexaEvt/IDOAlexaEvtIntroduction.md)** |
|                                                              |

