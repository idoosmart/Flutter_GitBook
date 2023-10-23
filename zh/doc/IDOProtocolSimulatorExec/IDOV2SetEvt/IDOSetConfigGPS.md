### 设置gps信息


**Flutter示例：**

```dart
/// 设置夜间体温开关事件号
setTemperatureSwitch(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_temperature_switch),

/// 设置夜间体温开关
libManager.send(evt: CmdEvtType.setTemperatureSwitch, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名              | 字段类型 | 字段说明                                                     |
| ------------------- | -------- | ------------------------------------------------------------ |
| utc_year            | int      | 时间 年                                                      |
| utc_month           | int      | 时间 月                                                      |
| utc_day             | int      | 时间 日                                                      |
| utc_hour            | int      | 时间 时                                                      |
| utc_minute          | int      | 时间 分                                                      |
| utc_second          | int      | 时间 秒                                                      |
| start_mode          | int      | 启动模式<br />1 冷启动<br />2 热启动  <br />默认2            |
| gsop_operation_mode | int      | 操作模式<br />1：正常<br />2：低功耗<br />4：为Balance<br />5：1PPS <br />默认1 |
| gsop_cycle_ms       | int      | 定位周期<br />默认1000 1s                                    |
| gns_value           | int      | 定位星mode<br />1：GPS<br />2：GLONASS<br />3：1为GPS + GLONASS<br />默认1 |

`示例：`

```c
{
  "utc_year":2022,
  "utc_month":12,
  "utc_day":19,
  "utc_hour":16,
  "utc_minute":18,
  "utc_second":30,
  "start_mode":2,
  "gsop_operation_mode":1,
  "gsop_cycle_ms":1000,
  "gns_value":1
}
```

