### 设置科学睡眠开关


功能表：setScientificSleepSwitch

**Flutter示例：**

```dart
/// 设置科学睡眠开关事件号
setScientificSleepSwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_scientific_sleep_switch),

/// 设置科学睡眠开关
libManager.send(evt: CmdEvtType.setScientificSleepSwitch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                |
| ------------ | -------- | --------------------------------------- |
| mode         | int      | 模式 <br />2：科学睡眠<br />1：普通睡眠 |
| start_hour   | int      | 开始时间 时                             |
| start_minute | int      | 开始时间 分                             |
| end_hour     | int      | 结束时间 时                             |
| end_minute   | int      | 结束时间 分                             |

`示例：`

```c
{
  "mode":1,
    "start_hour":23,
    "start_minute":0,
    "end_hour":9,
    "end_minute":0
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
