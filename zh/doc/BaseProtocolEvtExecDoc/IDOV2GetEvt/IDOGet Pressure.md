### 获取压力


功能表: getSupportGetPressureSwitchInfo

**Flutter示例：**

```dart
/// 获取压力事件号

/// 获取压力
libManager.send(evt: CmdEvtType.getStressSwitch, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| on_off           | int      | 开关状态<br />1:开启<br />0:关闭<br />-1:无效                |
| start_hour       | int      | 开关时间段/提醒时间段 开始时间 时                            |
| start_minute     | int      | 开关时间段/提醒时间段 开始时间 分                            |
| end_hour         | int      | 开关时间段/提醒时间段 结束时间 时                            |
| end_minute       | int      | 开关时间段/提醒时间段 结束时间 分                            |
| remind_on_off    | int      | 压力提醒<br />1:开启<br />0:关闭<br />-1:无效                |
| repeat           | int      | 预留                                                         |
| interval         | int      | 提醒间隔<br />单位分钟<br />默认60分钟                       |
| high_threshold   | int      | 压力过高阈值                                                 |
| stress_threshold | int      | 通知类型<br />0：无效<br />1：允许通知<br />2：静默通知<br />3：关闭通知<br />功能表`getPressureNotifyFlagMode` 开启有效 |
| notify_flag      | int      | 阈值<br />功能表`v2SendCalibrationThreshold` 开启有效        |
| measurement_interval | int | 测量间隔，单位：分钟 <br />可选择间隔10min/20min/30min（默认30min） |

`示例：`

```c
{
  "on_off": 1,
  "start_hour": 0,
  "start_minute": 0,
  "end_hour": 23,
  "end_minute": 59,
  "remind_on_off": 1,
  "repeat": 0,
  "interval": 60,
  "high_threshold": 80,
  "stress_threshold": 80,
  "notify_flag": 1,
  "measurement_interval": 5
}
```

