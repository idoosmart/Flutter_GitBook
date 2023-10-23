### 设置喝水提醒 


功能表：DrinkWaterReminder 【setNoReminderOnDrinkReminder，setDrinkWaterAddNotifyFlag】

**Flutter示例：**

```dart
/// 设置喝水提醒事件号
setDrinkWaterRemind(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_drink_water_reminder),

/// 设置喝水提醒
libManager.send(evt: CmdEvtType.setDrinkWaterRemind, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                  | 字段类型 | 字段说明                                                     |
| ----------------------- | -------- | ------------------------------------------------------------ |
| on_off                  | int      | 开关<br />0 关<br />1 开                                     |
| start_hour              | int      | 开始时间 时                                                  |
| start_minute            | int      | 开始时间 分                                                  |
| end_hour                | int      | 结束时间 时                                                  |
| end_minute              | int      | 结束时间 分                                                  |
| repeat                  | int      | 重复<br />bit0 无效<br />bit1-bit7 分别是星期1到星期7<br />0 不重复 1重复 |
| interval                | int      | 提醒间隔<br />单位分钟                                       |
| notify_flag             | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知   <br />需要固件开启功能表支持  `setDrinkWaterAddNotifyFlag` |
| do_not_disturb_on_off   | int      | 免提醒开关 00关 01开<br />需要固件开启功能表支持 `setNoReminderOnDrinkReminder` |
| no_disturb_start_hour   | int      | 免提醒开始时间 时<br />需要固件开启功能表支持 `setNoReminderOnDrinkReminder` |
| no_disturb_start_minute | int      | 免提醒开始时间 分<br />需要固件开启功能表支持 `setNoReminderOnDrinkReminder` |
| no_disturb_end_hour     | int      | 免提醒结束时间 时<br />需要固件开启功能表支持 `setNoReminderOnDrinkReminder` |
| no_disturb_end_minute   | int      | 免提醒结束时间 分<br />需要固件开启功能表支持 `setNoReminderOnDrinkReminder` |

`示例：`

```c
{
   "on_off":1,
   "start_hour":18,
   "start_minute":7,
   "end_hour":23,
   "end_minute":12,
   "repeat":127,
   "interval":20,
   "notify_flag":1,
   "do_not_disturb_on_off":1,
   "no_disturb_start_hour":9,
   "no_disturb_start_minute":0,
   "no_disturb_end_hour":12,
   "no_disturb_end_minute":0
}
```

