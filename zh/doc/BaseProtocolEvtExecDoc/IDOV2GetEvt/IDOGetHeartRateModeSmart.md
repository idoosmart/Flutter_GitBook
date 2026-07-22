### 获取智能心率模式


功能表: getSupportGetSmartHeartRate

**Flutter示例：**

```dart
/// 获取智能心率模式事件号

/// 获取智能心率模式
libManager.send(evt: CmdEvtType.getHeartRateModeSmart, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| mode             | int      | 开关状态<br />1:开启<br />0:关闭<br />-1:无效                |
| notify_flag      | int      | 通知类型<br />0：无效<br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| high_heart_mode  | int      | 智能心率过高提醒开关<br />1:开启<br />0:关闭<br />-1:无效    |
| low_heart_mode   | int      | 智能心率过低提醒开关<br />1:开启<br />0:关闭<br />-1:无效    |
| high_heart_value | int      | 智能心率过高提醒阈值                                         |
| low_heart_value  | int      | 智能心率过低提醒阈值                                         |
| start_hour       | int      | 心率监测时间段设置 开始时间 时                               |
| start_minute     | int      | 心率监测时间段设置 开始时间 分                               |
| end_hour         | int      | 心率监测时间段设置 结束时间 时                               |
| end_minute       | int      | 心率监测时间段设置 结束时间 分                               |
| measurement_interval | int | 测量间隔，单位：秒 |

`示例：`

```c
{
  "mode": 1,
  "notify_flag": 1,
  "high_heart_mode": 1,
  "low_heart_mode": 1,
  "high_heart_value": 100,
  "low_heart_value": 60,
  "start_hour": 0,
  "start_minute": 0,
  "end_hour": 23,
  "end_minute": 59,
  "measurement_interval": 300
}
```

