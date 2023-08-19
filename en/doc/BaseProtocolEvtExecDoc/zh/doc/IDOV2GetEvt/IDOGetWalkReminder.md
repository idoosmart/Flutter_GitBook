### 获取走动提醒


功能表:getWalkReminderV3

**Flutter示例：**

```dart
/// 获取走动提醒事件号
getWalkRemind(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_walk_reminder),

/// 获取走动提醒
libManager.send(evt: CmdEvtType.getWalkRemind, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                  | 字段类型 | 字段说明                                                     |
| ----------------------- | -------- | ------------------------------------------------------------ |
| on_off                  | int      | 0 关<br />1 开                                         |
| goal_step               | int      | 目标步数     <br />废弃                                      |
| start_hour              | int      | 开始时间 时                                                  |
| start_minute            | int      | 开始时间 分                                                  |
| end_hour                | int      | 结束时间 时                                                  |
| end_minute              | int      | 结束时间 分                                                  |
| repeat                  | int      | 重复<br />bit1-bit7 周一到周日， bit 0是总开关位（开关）                                                        |
| goal_time               | int      | 目标时间     <br />废弃                                      |
| notify_flag             | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知<br />需要固件开启功能表<br />V3_walk_reminder_add_notify_flag |
| do_not_disturb_on_off   | int      | 免提醒开关<br />0 关 <br />1开<br />需要固件开启功能表<br />v2_support_set_get_no_reminder_on_walk_reminder |
| no_disturb_start_hour   | int      | 免提醒开始时间 时<br />需要固件开启功能表<br />v2_support_set_get_no_reminder_on_walk_reminder |
| no_disturb_start_minute | int      | 免提醒开始时间 分<br />需要固件开启功能表<br />v2_support_set_get_no_reminder_on_walk_reminder |
| no_disturb_end_hour     | int      | 免提醒结束时间 时<br />需要固件开启功能表<br />v2_support_set_get_no_reminder_on_walk_reminder |
| no_disturb_end_minute   | int      | 免提醒结束时间 分<br />需要固件开启功能表<br />v2_support_set_get_no_reminder_on_walk_reminder |

`示例：`

```c
{
  "on_off" : 0,
  "goal_step" : 0,
  "start_hour" : 18,
  "start_minute" : 0,
  "end_hour" : 23,
  "end_minute" : 0,
  "repeat" : 127,
  "goal_time" : 0,
  "notify_flag" : 2,
  "do_not_disturb_on_off" : 0,
  "no_disturb_start_hour" : 0,
  "no_disturb_start_minute" : 0,
  "no_disturb_end_hour" : 0,
  "no_disturb_end_minute" : 0
}
```

