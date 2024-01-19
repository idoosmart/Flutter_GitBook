### 设置智能心率模式


功能表：setSmartHeartRate

**Flutter示例：**

```dart
/// 智能心率模式设置事件号
setHeartRateModeSmart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_heart_rate_mode_smart),

/// 智能心率模式设置
libManager.send(evt: CmdEvtType.setHeartRateModeSmart, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| mode             | int      | 开关：<br />0:关<br />1:开                                   |
| notify_flag      | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知 |
| high_heart_mode  | int      | 1：开启智能心率过高提醒开关<br />0：关闭                     |
| low_heart_mode   | int      | 1：开启智能心率过低提醒开关<br />0：关闭                     |
| high_heart_value | int      | 智能心率过高提醒阈值                                         |
| low_heart_value  | int      | 智能心率过低提醒阈值                                         |
| start_hour       | int      | 心率监测时间段设置<br />开始时间 时                          |
| start_minute     | int      | 开始时间 分                                                  |
| end_hour         | int      | 结束时间 时                                                  |
| end_minute       | int      | 结束时间 分                                                  |

`示例：`

```json
{
  "mode":1,
  "notify_flag":0,
  "high_heart_mode":0,
  "low_heart_mode":0,
  "high_heart_value":100,
  "low_heart_value":80,
  "start_hour":9,
  "start_minute":0,
  "end_hour":12,
  "end_minute":0
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明               |
| -------- | -------- | ---------------------- |
| err_code | int      | 0成功<br />非0是错误码 |

`示例：`
```c
{
  "err_code":0
}
```