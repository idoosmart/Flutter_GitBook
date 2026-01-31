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

| 字段名              | 字段类型 | 字段说明                                                     |
| ------------------- | -------- | ------------------------------------------------------------ |
| mode                | int      | 模式 <br />2：科学睡眠<br />1：普通睡眠                      |
| start_hour          | int      | 开始时间 时                                                  |
| start_minute        | int      | 开始时间 分                                                  |
| end_hour            | int      | 结束时间 时                                                  |
| end_minute          | int      | 结束时间 分                                                  |
| sleep_remind_switch | int      | 睡眠提醒开关 1开,  0关闭 ,(功能表`supportSetSleepRemind`开启时有效) |
| sleep_remind_hour   | int      | 睡眠提醒时间(小时) ,(功能表`supportSetSleepRemind`开启时有效) |
| sleep_remind_minute | int      | 睡眠提醒时间(分钟) ,(功能表`supportSetSleepRemind`开启时有效) |
| repetitions         | int      | 重复周期，bit0预留，bit1~bit7分别是星期1到星期7，1重复，0不重复 , (功能表`supportSetSleepRemind`开启时有效) |

`示例：`

```c
{
	"mode": 1,
	"start_hour": 23,
	"start_minute": 0,
	"end_hour": 9,
	"end_minute": 0,
	"sleep_remind_switch": 1,
	"sleep_remind_hour": 22,
	"sleep_remind_minute": 11,
	"repetitions": 127
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
