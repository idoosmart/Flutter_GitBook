### 设置经期


功能表：setMenstruation 【getMenstrualAddNotifyFlagV3，support_set_menstrual_on_off(SDK待补充)】

**Flutter示例：**

```dart
/// 设置经期事件号
setMenstruation(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_menstruation),

/// 设置经期
libManager.send(evt: CmdEvtType.setMenstruation, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名                 | 字段类型 | 字段说明                                                     |
| ---------------------- | -------- | ------------------------------------------------------------ |
| on_off                 | int      | 经期提醒开关 <br />170开,85关闭                              |
| menstrual_length       | int      | 经期长度                                                     |
| menstrual_cycle        | int      | 经期周期                                                     |
| last_menstrual_year    | int      | 最近一次经期开始时间 年                                      |
| last_menstrual_month   | int      | 最近一次经期开始时间 月                                      |
| last_menstrual_day     | int      | 最近一次经期开始时间 日                                      |
| ovulation_interval_day | int      | 从下一个经期开始前到排卵日的间隔,一般为14天                  |
| ovulation_before_day   | int      | 排卵日之前易孕期的天数,一般为5                               |
| ovulation_after_day    | int      | 排卵日之后易孕期的天数,一般为5                               |
| notify_flag            | int      | 通知类型 <br />0：无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知<br />需要固件开启功能表支持 V3_menstrual_add_notify_flag |
| menstrual_on_off       | int      | 经期开关<br />170开,85关闭<br />需要固件开启功能表支持 support_set_menstrual_on_off |

`示例：`

```c
{
   "on_off":170,
   "menstrual_length":7,
   "menstrual_cycle":21,
   "last_menstrual_year":2022,
   "last_menstrual_month":12,
   "last_menstrual_day":19,
   "ovulation_interval_day":15,
   "ovulation_before_day":5,
   "ovulation_after_day":5,
   "notify_flag":1
}
```

