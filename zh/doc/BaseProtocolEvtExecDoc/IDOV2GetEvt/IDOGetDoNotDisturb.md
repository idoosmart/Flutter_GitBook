### 获取勿扰模式状态


功能表:getDoNotDisturbMain3

**Flutter示例：**

```dart
/// 获取勿扰模式状态事件号
getNotDisturbStatus(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_do_not_disturb),

/// 获取勿扰模式状态
libManager.send(evt: CmdEvtType.getNotDisturbStatus, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                     | 字段类型 | 字段说明                                                     |
| -------------------------- | -------- | ------------------------------------------------------------ |
| switch_flag                | int      | 开关状态<br />1 开启<br />0 关闭<br />-1 不支持              |
| start_hour                 | int      | 开始时间 时                                                  |
| start_minute               | int      | 开始时间 分                                                  |
| end_hour                   | int      | 结束时间 时                                                  |
| end_minute                 | int      | 结束时间 分                                                  |
| have_time_range            | int      | 是否有时间范围 <br />0 无效<br />1 表示无时间范围<br />2 表示有时间范围 |
| week_repeat                | int      | 预留                                                         |
| noontime_rest_on_off       | int      | 午休开关<br />免提醒开关<br />1 开启<br />0 关闭<br />-1 不支持 |
| noontime_rest_start_hour   | int      | 提醒开始时间 时                                              |
| noontime_rest_start_minute | int      | 提醒开始时间 分                                              |
| noontime_rest_end_hour     | int      | 提醒结束时间 时                                              |
| noontime_rest_end_minute   | int      | 提醒结束时间 分                                              |
| all_day_on_off             | int      | 全天勿扰开关<br />1 开启<br />0 关闭<br />-1 不支持          |
| intelligent_on_off         | int      | 智能勿扰开关<br />1 开启<br />0 关闭<br />-1 不支持          |

`示例：`

```c
{
  "all_day_on_off" : 0,
  "end_hour" : 7,
  "end_minute" : 0,
  "have_time_range" : 0,
  "intelligent_on_off" : 0,
  "noontime_rest_end_hour" : 7,
  "noontime_rest_end_minute" : 0,
  "noontime_rest_on_off" : 1,
  "noontime_rest_start_hour" : 22,
  "noontime_rest_start_minute" : 0,
  "start_hour" : 22,
  "start_minute" : 0,
  "switch_flag" : 1,
  "week_repeat" : 0
}
```

