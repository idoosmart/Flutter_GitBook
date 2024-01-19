### 设置洗手提醒


功能表：setHandWashReminder

**Flutter示例：**

```dart
/// 设置洗手提醒事件号
setHandWashingReminder(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_set_hand_washing_reminder),

/// 设置洗手提醒
libManager.send(evt: CmdEvtType.setHandWashingReminder, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                    |
| ------------ | -------- | ------------------------------------------- |
| on_off       | int      | 0：关<br />1：开 <br />默认是关闭     |
| start_hour   | int      | 提醒开始时间 时                             |
| start_minute | int      | 提醒开始时间 分                             |
| end_hour     | int      | 提醒结束时间 时                             |
| end_minute   | int      | 提醒结束时间 分                             |
| repeat       | int      | bit0 无效<br />bit1-bit7 分别是星期1到星期7 |
| interval     | int      | 提醒间隔 单位分钟 <br />默认60分钟          |


`示例：`
```c
{
  "on_off":0,
    "start_hour":0,
    "start_minute":0,
    "end_hour":0,
    "end_minute":0,
    "repeat":0,
    "interval":0
}
```


**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`
```c
{
  "is_success":1
}
```
