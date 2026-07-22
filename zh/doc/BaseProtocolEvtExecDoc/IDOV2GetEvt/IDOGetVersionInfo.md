### 获取版本信息


功能表:getVersionInfo

**Flutter示例：**

```dart
/// 获取版本信息事件号
getVersionInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_version_info),

/// 获取版本信息
libManager.send(evt: CmdEvtType.getVersionInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                      | 字段类型 | 字段说明                           |
| --------------------------- | -------- | ---------------------------------- |
| sdk_version                 | int      |                                    |
| hr_algorithm_version        | int      | 心率算法版本                       |
| sleep_algorithm_version     | int      | 睡眠算法版本                       |
| step_algorithm_version      | int      | 计步算法版本                       |
| gesture_recognition_version | int      | 手势识别算法版本                   |
| pcb_version                 | int      | PCB 版本 数值为x10,11表示1.1的版本 |
| spo2_version                | int      | 穿戴版本                           |
| wear_version                | int      | 血氧算法版本                       |
| stress_version              | int      | 压力算法版本                       |
| kcal_version                | int      | 卡路里算法版本                     |
| dis_version                 | int      | 距离算法版本                       |
| axle3_swim_version          | int      | 三轴传感器游泳算法版本             |
| axle6_swim_version          | int      | 六轴传感器游泳算法版本             |
| act_mode_type_version       | int      | 运动自识别算法版本                 |
| all_day_hr_version          | int      | 全天心率算法版本                   |
| gps_version                 | int      | gps算法版本                        |
| peripherals_version         | int      | 外设版本 206定制项目外设版本       |

`示例：`

```c
{
  "act_mode_type_version" : 10,
  "all_day_hr_version" : 45,
  "axle3_swim_version" : 19,
  "axle6_swim_version" : 19,
  "dis_version" : 4,
  "gesture_recognition_version" : 33,
  "gps_version" : 0,
  "hr_algorithm_version" : 45,
  "kcal_version" : 5,
  "pcb_version" : 1,
  "peripherals_version" : 0,
  "sdk_version" : 15,
  "sleep_algorithm_version" : 1,
  "spo2_version" : 24,
  "step_algorithm_version" : 25,
  "stress_version" : 4,
  "wear_version" : 22
}
```

