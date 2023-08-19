### 设置勿扰模式


功能表: setDoNotDisturb 【disturbHaveRangRepeat(SDk待补充)，setOnlyNoDisturbAllDayOnOff，setOnlyNoDisturbSmartOnOff】

**Flutter示例：**

```dart
/// 设置勿扰模式事件号
setNotDisturb(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_do_not_disturb),

/// 设置勿扰模式
libManager.send(evt: CmdEvtType.setNotDisturb, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                     | 字段类型 | 字段说明                                                     |
| -------------------------- | -------- | ------------------------------------------------------------ |
| switch_flag                | int      | 模式<br />0：默认，1：横屏， 2:竖屏， 3：（翻转180度） |
| start_hour                 | int      | 开始时间<br />时                                             |
| start_minute               | int      | 开始时间<br />分                                             |
| end_hour                   | int      | 结束时间<br />时                                             |
| end_minute                 | int      | 结束时间<br />分                                             |
| have_time_range            | int      | 是否有时间范围 <br />0 无效,1 表示无时间范围,2 表示有时间范围 |
| week_repeat                | int      | 星期重复和久坐,闹钟一样<br />bit0无效,(bit1 - bit7) 对于星期1到星期天 |
| noontime_rest_on_off       | int      | 白天勿扰开关 <br />170 开启,85 关闭                       |
| noontime_rest_start_hour   | int      | 开始时间<br />时                                             |
| noontime_rest_start_minute | int      | 开始时间<br />分                                             |
| noontime_rest_end_hour     | int      | 结束时间<br />时                                             |
| noontime_rest_end_minute   | int      | 结束时间<br />分                                             |
| all_day_on_off             | int      | 全天勿扰 <br />170 开启,85 关闭                           |
| intelligent_on_off         | int      | 智能勿扰开关 <br />170 开启,85 关闭                       |

`示例：`

```c
{
  "switch_flag":0,
  "start_hour":15,
  "start_minute":23,
  "end_hour":23,
  "end_minute":30,
  "have_time_range":2,
  "week_repeat":127,
  "noontime_rest_on_off":170,
  "noontime_rest_start_hour":9,
  "noontime_rest_start_minute":0,
  "noontime_rest_end_hour":12,
  "noontime_rest_end_minute":0,
  "all_day_on_off":85,
  "intelligent_on_off":85
}
```
