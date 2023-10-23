### 获取心率监测模式


功能表:getHeartRateModeV2

**Flutter示例：**

```dart
/// 获取心率监测模式事件号
getHeartRateMode(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_heart_rate_mode),

/// 获取心率监测模式
libManager.send(evt: CmdEvtType.getHeartRateMode, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| mode                 | int      | 0:关闭<br />1:手动模式<br />2:自动<br />3:持续监测<br />-1:无效 |
| has_time_range       | int      | 是否有时间区间 0 无,1 有                                     |
| start_hour           | int      | 开始时间 时                                                  |
| start_minute         | int      | 开始时间 分                                                  |
| end_hour             | int      | 结束时间 时                                                  |
| end_minute           | int      | 结束时间 分                                                  |
| measurement_interval | int      | 测量间隔<br />单位分钟                                       |

`示例：`

```c
{
    "mode":1,
    "has_time_range":0,
    "start_hour":9,
    "start_minute":0,
    "end_hour":12,
    "end_minute":0,
    "measurement_interval":15
}
```

