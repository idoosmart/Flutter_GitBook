### 设置走动提醒


功能表：setWalkReminder 【setWalkReminderAddNotify，v2SupportSetGetNoReminderOnWalkReminder】

**Flutter示例：**

```dart
/// 设置走动提醒事件号
setWalkRemind(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_walk_reminder),

/// 设置走动提醒
libManager.send(evt: CmdEvtType.setWalkRemind, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                  | 字段类型 | 字段说明                                                     |
| ----------------------- | -------- | ------------------------------------------------------------ |
| on_off                  | int      | 开关<br />0 关,1 开                                          |
| goal_step               | int      | 目标步数<br />预留                                           |
| start_hour              | int      | 开始时间 时                                                  |
| start_minute            | int      | 开始时间 分                                                  |
| end_hour                | int      | 结束时间 时                                                  |
| end_minute              | int      | 结束时间 分                                                  |
| repeat                  | int      | 重复<br />bit0无效<br />bit1-bit7分别是星期1到星期7，0不重复 1重复 |
| goal_time               | int      | 目标时间  <br />预留                                         |
| notify_flag             | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知   <br />需要固件开启功能表支持`setWalkReminderAddNotify` |
| do_not_disturb_on_off   | int      | 走动勿扰(免提醒)开关<br />0关 1开<br />需要固件开启功能表支持 `v2SupportSetGetNoReminderOnWalkReminder` |
| no_disturb_start_hour   | int      | 开始时间 时<br />需要固件开启功能表支持 `v2SupportSetGetNoReminderOnWalkReminder` |
| no_disturb_start_minute | int      | 开始时间 分<br />需要固件开启功能表支持 `v2SupportSetGetNoReminderOnWalkReminder` |
| no_disturb_end_hour     | int      | 结束时间 时<br />需要固件开启功能表支持 `v2SupportSetGetNoReminderOnWalkReminder` |
| no_disturb_end_minute   | int      | 结束时间 分<br />需要固件开启功能表支持 `v2SupportSetGetNoReminderOnWalkReminder` |

`示例：`

```c
{
   "on_off":1,
   "goal_step":2000,
   "start_hour":14,
   "start_minute":0,
   "end_hour":20,
   "end_minute":0,
   "repeat":127,
   "goal_time":60,
   "notify_flag":1,
   "do_not_disturb_on_off":0,
   "no_disturb_start_hour":0,
   "no_disturb_start_minute":0,
   "no_disturb_end_hour":0,
   "no_disturb_end_minute":0
}
```

