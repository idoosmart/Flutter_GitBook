### 获取电池信息


功能表:getBatteryInfo

**Flutter示例：**

```dart
/// 获取电池信息事件号
getBatteryInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_batt_info),

/// 获取电池信息
libManager.send(evt: CmdEvtType.getBatteryInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名               | 字段类型 | 字段说明                                                     |
| -------------------- | -------- | ------------------------------------------------------------ |
| type                 | int      | 电池类型：0：可充电锂电池， 1：纽扣电池                |
| voltage              | int      | 电量                                                         |
| status               | int      | 电池状态<br />0：正常<br />1：正在充电<br />2：充电完成<br />3：低电量 |
| level                | int      | 等级                                                         |
| last_charging_year   | int      | 最后一次充电时间 年                                          |
| last_charging_month  | int      | 最后一次充电时间 月                                          |
| last_charging_day    | int      | 最后一次充电时间 日                                          |
| last_charging_hour   | int      | 最后一次充电时间 时                                          |
| last_charging_minute | int      | 最后一次充电时间 分                                          |
| last_charging_second | int      | 最后一次充电时间 秒                                          |
| mode                 | int      | 0：无效<br />1：正常模式（非省电模式） <br />2：省电模式 |

`示例：`

```c
{
  "last_charging_day" : 0,
  "last_charging_hour" : 158,
  "last_charging_minute" : 66,
  "last_charging_month" : 0,
  "last_charging_second" : 0,
  "last_charging_year" : 0,
  "level" : 100,
  "mode" : 0,
  "status" : 0,
  "type" : 0,
  "voltage" : 4317
}
```

