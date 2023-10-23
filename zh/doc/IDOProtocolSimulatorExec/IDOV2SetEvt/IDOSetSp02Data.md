### 设置血氧开关


功能表：setSpo2Data【setSpo2AllDayOnOff，v3SupportSetSpo2LowValueRemind(SDK待补充)，getSpo2NotifyFlag】

**Flutter示例：**

```dart
/// 设置血氧开关事件号
setSpo2Switch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_spo2),

/// 设置血氧开关
libManager.send(evt: CmdEvtType.setSpo2Switch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| on_off          | int      | 全天血氧开关 <br />1开 0关闭                                 |
| start_hour      | int      | 开始时间 时                                                  |
| start_minute    | int      | 开始时间 分                                                  |
| end_hour        | int      | 结束时间 时                                                  |
| end_minute      | int      | 结束时间 分                                                  |
| low_spo2_on_off | int      | 血氧过低开关 <br />1开 0关闭<br />需要功能表支持V3_support_set_spo2_low_value_remind |
| low_spo2_value  | int      | 血氧过低阈值<br />需要功能表支持V3_support_set_spo2_low_value_remind |
| notify_flag     | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知  <br />需要功能表支持 V3_spo2_add_notify_flag |

`示例：`

```c
{
   "on_off":1,
   "start_hour":14,
   "start_minute":0,
   "end_hour":20,
   "end_minute":0,
   "low_spo2_on_off":1,
   "low_spo2_value":20,
   "notify_flag":1
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明             |
| -------- | -------- | -------------------- |
| err_code | int      | 0是成功，非0是错误码 |

`示例：`

```c
{
   "err_code":0
}
```

