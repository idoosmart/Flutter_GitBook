### 设置心率模式


功能表：syncHeartRateMonitor 【exTableMain7HeartRateInterval(SDk待补充)】

**Flutter示例：**

```dart
/// 设置心率模式事件号
setHeartRateMode(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_heart_rate_mode),

/// 设置心率模式
libManager.send(evt: CmdEvtType.setHeartRateMode, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| mode                 | int      | 170：手动模式<br />85：关闭<br />136：自动<br />153：持续监测 |
| has_time_range       | int      | 时间区间<br />0：无<br />1：有                         |
| start_hour           | int      | 开始时间时（24小时制0~23）                                   |
| start_minute         | int      | 开始时间分（0~59）                                           |
| end_hour             | int      | 结束时间时                                                   |
| end_minute           | int      | 结束时间分                                                   |
| measurement_interval | int      | 测量间隔<br />单位分钟                                       |

`示例：`

```c
{
  "mode":170,
  "has_time_range":1,
  "start_hour":10,
  "start_minute":30,
  "end_hour":20,
  "end_minute":30,
  "measurement_interval":15
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

