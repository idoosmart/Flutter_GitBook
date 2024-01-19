### 设置吃药提醒


功能表：exTableMain11TakingMedicine(SDK待补充)

**Flutter示例：**

```dart
/// 设置吃药提醒事件号
setTakingMedicineReminder(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_taking_medicine_reminder),

/// 设置吃药提醒
libManager.send(evt: CmdEvtType.setTakingMedicineReminder, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                      | 字段类型 | 字段说明                                                     |
| --------------------------- | -------- | ------------------------------------------------------------ |
| taking_medicine_id          | int      | id 从1开始  最多5个                                          |
| on_off                      | int      | 0：关<br />1：开 <br />默认是关闭                      |
| start_hour                  | int      | 提醒开始时间 时                                              |
| start_minute                | int      | 提醒开始时间 分                                              |
| end_hour                    | int      | 提醒结束时间 时                                              |
| end_minute                  | int      | 提醒结束时间 分                                              |
| repeat                      | int      | bit0 无效<br />bit1-bit7 分别是星期1到星期7                  |
| interval                    | int      | 提醒间隔 单位分钟 <br />默认60分钟                           |
| do_not_disturb_on_off       | int      | 免提醒时间段开关<br />0：关<br />1：开 <br />默认是关闭 |
| do_not_disturb_start_hour   | int      | 勿扰开始时间 时                                              |
| do_not_disturb_start_minute | int      | 勿扰开始时间 分                                              |
| do_not_disturb_end_hour     | int      | 勿扰结束时间 时                                              |
| do_not_disturb_end_minute   | Int      | 勿扰结束时间 分                                              |

`示例：`

```c
{
  "taking_medicine_id":1,
  "on_off":0,
  "start_hour":10,
  "start_minute":22,
  "end_hour":23,
  "end_minute":0,
  "repeat":127,
  "interval":60,
  "do_not_disturb_on_off":0,
  "do_not_disturb_start_hour":0,
  "do_not_disturb_start_minute":0,
  "do_not_disturb_end_hour":0,
  "do_not_disturb_end_minute":0
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`
```c
{
  "is_success":0
}
```
