### V3设置心率模式


功能表:setSmartHeartRate

**Flutter示例：**

```dart
// 设置心率模式事件号
setHeartMode(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_hr_mode),

/// 设置心率模式
libManager.send(evt: CmdEvtType.setHeartMode, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| update_time          | int      | 更新时间unix 时间戳,秒级 <br />等于0是获取，当前的utc时间挫是设置  |
| mode                 | int      | 模式<br />136 ：自动（5分钟）<br />153 ：持续监测（5S）<br />85 ：关闭 不起作用<br />204 ：设置对应的measurement_interval<br />170 ：手动模式(关闭自动)<br />187 ：默认的类型<br />187这个是app设置这个下来，固件自动设置成默认的模式，<br />如果配置了功能表support_set_v3_heart_interval，85&136&153 持续监测设置无效 <br />快速配置的时候，配置support_set_v3_heart_interval， 204设置起作用<br />设置连续心率的时候，如果配置support_set_v3_heart_interval这个功能，对应的设置mode是204 |
| has_time_range       | int      | 是否有时间区间 0 无,1 有                                 |
| start_hour           | int      | 起始时间 时                                                  |
| start_minute         | int      | 起始时间 分                                                  |
| end_hour             | int      | 结束时间 时                                                  |
| end_minute           | int      | 结束时间 分                                                  |
| measurement_interval | int      | 测量间隔 单位秒                                              |
| notify_flag          | int      | 通知类型 <br />0无效 ； 1：允许通知； 2：静默通知； 3：关闭通知<br />固件未开启v3_heart_set_rate_mode_custom设置无效 |
| high_heart_mode      | int      | 170:开启智能心率过高提醒开关， 85:关闭<br />固件未开启v3_heart_set_rate_mode_custom设置无效 |
| low_heart_mode       | int      | 170:开启智能心率过低提醒开关， 85:关闭<br />固件未开启v3_heart_set_rate_mode_custom设置无效 |
| high_heart_value     | int      | 智能心率过高提醒阈值<br />固件未开启v3_heart_set_rate_mode_custom设置无效 |
| low_heart_value      | int      | 智能心率过低提醒阈值<br />固件未开启v3_heart_set_rate_mode_custom设置无效 |

`示例：`

```c
{
    "update_time":0,
    "mode":0,
    "has_time_range":0,
    "start_hour":0,
    "start_minute":0,
    "end_hour":0,
    "end_minute":0,
    "measurement_interval":0,
    "notify_flag":0,
    "high_heart_mode":0,
    "low_heart_mode":0,
    "high_heart_value":0,
    "low_heart_value":0
}
```

**App收到的json字段**：

| 字段名              | 字段类型 | 字段说明                                                     |
| ------------------- | -------- | ------------------------------------------------------------ |
| update_time         | int      | 更新时间unix 时间戳,秒级<br />等于0是获取，当前的utc时间挫是设置   |
| mode                | int      | 模式<br />136 ：自动（5分钟）<br />153 ：持续监测（5S）<br />85 ：关闭 不起作用<br />204 ：设置对应的measurement_interval<br />170 ：手动模式(关闭自动)<br />187 ：默认的类型<br />187这个是app设置这个下来，固件自动设置成默认的模式，<br />如果配置了功能表support_set_v3_heart_interval，85&136&153 持续监测设置无效 <br />快速配置的时候，配置support_set_v3_heart_interval， 204设置起作用<br />设置连续心率的时候，如果配置support_set_v3_heart_interval这个功能，对应的设置mode是204 |
| has_time_range      | int      | 是否有时间区间 0 无,1 有                                 |
| start_hour          | int      | 起始时间 时                                                  |
| start_minute        | int      | 起始时间 分                                                  |
| end_hour            | int      | 结束时间 时                                                  |
| end_minute          | int      | 结束时间 分                                                  |
| measurementInterval | int      | 测量间隔 单位秒                                              |
| get_sec_mode        | int      | 目前手表支持的心率类型，全0 无效值，bit0：5s模式<br />固件未开启support_set_v3_heart_interval则返回0 |
| get_min_mode        | int      | 目前手表支持的心率类型，全0 无效值，bit0：1分钟， bit1 ：3分钟； bit2：5分钟； bit3：10分钟； bit4：30分钟  bit5：285模式  bit6：15分钟模式<br />固件未开启support_set_v3_heart_interval则返回0 |
| notify_flag         | int      | 通知类型 ： <br />0无效 ； 1：允许通知； 2：静默通知； 3：关闭通知<br />固件未开启v3_heart_set_rate_mode_custom则返回0 |
| high_heart_mode     | int      | 170:开启智能心率过高提醒开关， 85:关闭<br />固件未开启v3_heart_set_rate_mode_custom则返回0 |
| low_heart_mode      | int      | 170:开启智能心率过低提醒开关， 85:关闭<br />固件未开启v3_heart_set_rate_mode_custom则返回0 |
| high_heart_value    | int      | 智能心率过高提醒阈值<br />固件未开启v3_heart_set_rate_mode_custom则返回0 |
| low_heart_value     | Int      | 智能心率过低提醒阈值<br />固件未开启v3_heart_set_rate_mode_custom则返回0 |

`示例：`

```c
{
    "update_time":0,
    "mode":204,
    "has_time_range":1,
    "start_hour":9,
    "start_minute":0,
    "end_hour":12,
    "end_minute":19,
    "measurement_interval":5,
    "notify_flag":2,
    "high_heart_mode":85,
    "low_heart_mode":85,
    "high_heart_value":0,
    "low_heart_value":0
}
```

