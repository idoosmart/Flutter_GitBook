### V3设置心率模式


功能表:setSmartHeartRate 【setSetV3HeartInterval，v3HeartSetRateModeCustom】

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
| update_time          | int      | 更新时间unix 时间戳,秒级 <br />等于0是获取，当前的utc时间挫是设置 |
| mode                 | int      | 模式<br />0 ：关闭<br />1 ：自动（5分钟）<br />2 ：持续监测（5S）<br />3 ：手动模式(关闭自动)<br />4 ：默认的类型,设置后固件自动设置成默认的模式<br />5 ：设置对应的measurement_interval<br />6 ：智能心率模式(ID206)<br />**备注：**<br />1.如果配置功能表`setSetV3HeartInterval`，`模式0`&`模式1`&`模式2`设置无效 <br />2.快速配置的时候，配置`setSetV3HeartInterval`， `模式5`设置起作用<br />3.设置连续心率的时候，如果配置`setSetV3HeartInterval`这个功能，对应的设置mode是`模式5` |
| has_time_range       | int      | 是否有时间区间 0 无,1 有                                     |
| start_hour           | int      | 起始时间 时                                                  |
| start_minute         | int      | 起始时间 分                                                  |
| end_hour             | int      | 结束时间 时                                                  |
| end_minute           | int      | 结束时间 分                                                  |
| measurement_interval | int      | 测量间隔 单位秒                                              |
| notify_flag          | int      | 通知类型 <br />0：无效<br />1：允许通知<br />2：静默通知<br />3：关闭通知<br />固件未开启`v3HeartSetRateModeCustom`设置无效 |
| high_heart_mode      | int      | 1:开启智能心率过高提醒开关<br />0:关闭<br />固件未开启`v3HeartSetRateModeCustom`设置无效 |
| low_heart_mode       | int      | 1:开启智能心率过低提醒开关<br /> 0:关闭<br />固件未开启`v3HeartSetRateModeCustom`设置无效 |
| high_heart_value     | int      | 智能心率过高提醒阈值<br />固件未开启`v3HeartSetRateModeCustom`设置无效 |
| low_heart_value      | int      | 智能心率过低提醒阈值<br />固件未开启`v3HeartSetRateModeCustom`设置无效 |

`APP查询心率模式示例：`

```json
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
| update_time         | int      | 更新时间unix 时间戳,秒级<br />等于0是获取，当前的utc时间挫是设置 |
| mode                | int      | 模式<br />0 ：关闭<br />1 ：自动（5分钟）<br />2 ：持续监测（5S）<br />3 ：手动模式(关闭自动)<br />4 ：默认的类型,设置后固件自动设置成默认的模式<br />5 ：设置对应的measurement_interval<br />6 ：智能心率模式(ID206)<br />-1：无效<br />**备注：**<br />1.如果配置功能表`setSetV3HeartInterval`，`模式0`&`模式1`&`模式2`设置无效 <br />2.快速配置的时候，配置`setSetV3HeartInterval`， `模式5`设置起作用<br />3.设置连续心率的时候，如果配置`setSetV3HeartInterval`这个功能，对应的设置mode是`模式5` |
| has_time_range      | int      | 是否有时间区间 0 无,1 有                                     |
| start_hour          | int      | 起始时间 时                                                  |
| start_minute        | int      | 起始时间 分                                                  |
| end_hour            | int      | 结束时间 时                                                  |
| end_minute          | int      | 结束时间 分                                                  |
| measurementInterval | int      | 测量间隔 单位秒                                              |
| get_sec_mode        | int      | 目前手表支持的心率类型<br />全0 ：无效值<br />bit0：5s模式<br />固件未开启`setSetV3HeartInterval`则返回0 |
| get_min_mode        | int      | 目前手表支持的心率类型<br />全0：无效值<br />bit0：1分钟<br />bit1 ：3分钟<br />bit2：5分钟<br />bit3：10分钟<br />bit4：30分钟<br />bit5：255模式<br />bit6：15分钟模式<br />固件未开启`setSetV3HeartInterval`则返回0 |
| notify_flag         | int      | 通知类型 ： <br />0无效 <br />1：允许通知<br />2：静默通知<br />3：关闭通知<br />固件未开启`v3HeartSetRateModeCustom`则返回0 |
| high_heart_mode     | int      | 1:开启智能心率过高提醒开关<br />0:关闭<br />固件未开启`v3HeartSetRateModeCustom`则返回0 |
| low_heart_mode      | int      | 1:开启智能心率过低提醒开关<br />0:关闭<br />固件未开启`v3HeartSetRateModeCustom`则返回0 |
| high_heart_value    | int      | 智能心率过高提醒阈值<br />固件未开启`v3HeartSetRateModeCustom`则返回0 |
| low_heart_value     | Int      | 智能心率过低提醒阈值<br />固件未开启`v3HeartSetRateModeCustom`则返回0 |

`Example of the device replying to query the heart rate mode：`

```json
{
    "update_time":0,
    "mode":5,
    "has_time_range":1,
    "start_hour":9,
    "start_minute":0,
    "end_hour":12,
    "end_minute":19,
    "measurement_interval":5,
    "notify_flag":2,
    "high_heart_mode":0,
    "low_heart_mode":0,
    "high_heart_value":0,
    "low_heart_value":0
}
```

