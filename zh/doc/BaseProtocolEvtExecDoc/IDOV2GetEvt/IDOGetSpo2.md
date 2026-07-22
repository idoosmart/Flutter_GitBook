### 获取血氧


功能表: getSupportGetSpo2SwitchInfo

**Flutter示例：**

```dart
/// 获取血氧事件号

/// 获取血氧
libManager.send(evt: CmdEvtType.getSpo2Switch, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| on_off          | int      | 开关状态<br />1:开启<br />0:关闭<br />-1:无效                |
| start_hour      | int      | 开始时间 时                                                  |
| start_minute    | int      | 开始时间 分                                                  |
| end_hour        | int      | 结束时间 时                                                  |
| end_minute      | int      | 结束时间 分                                                  |
| low_spo2_on_off | int      | 血氧过低开关状态<br />1:开启<br />0:关闭<br />-1:无效        |
| low_spo2_value  | int      | 血氧过低阈值                                                 |
| notify_flag     | int      | 通知类型<br />0：无效<br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| measurement_interval | int | 测量间隔，单位：分钟 <br />可选30/60/120min，开启后默认值为60min |

`示例：`

```c
{
  "on_off": 1,
  "start_hour": 0,
  "start_minute": 0,
  "end_hour": 23,
  "end_minute": 59,
  "low_spo2_on_off": 1,
  "low_spo2_value": 90,
  "notify_flag": 1,
  "measurement_interval": 5
}
```

