### 设置经期提醒


功能表：setMenstruation 【setMenstrualAddPregnancy，not_support_set_ovulation(SDK待补充)】

**Flutter示例：**

```dart
/// 设置经期提醒事件号
setMenstruationRemind(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_menstruation_remind),

/// 设置经期提醒
libManager.send(evt: CmdEvtType.setMenstruationRemind, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                      | 字段类型 | 字段说明                         |
| --------------------------- | -------- | -------------------------------- |
| start_day                   | int      | 开始日提醒  提前天数             |
| ovulation_day               | int      | 排卵日提醒 提前天数              |
| hour                        | int      | 提醒时间 时                      |
| minute                      | int      | 提醒时间 分                      |
| pregnancy_day_before_remind | int      | 易孕期 开始的时候 提前多少天提醒 |
| pregnancy_day_end_remind    | int      | 易孕期 结束的时候 提前多少天提醒 |
| menstrual_day_end_remind    | int      | 经期结束 提前多少天提醒          |

`示例：`


```c
{
   "start_day":5,
   "ovulation_day":5,
   "hour":21,
   "minute":0,
   "pregnancy_day_before_remind":5,
   "pregnancy_day_end_remind":5,
   "menstrual_day_end_remind":1
}
```

