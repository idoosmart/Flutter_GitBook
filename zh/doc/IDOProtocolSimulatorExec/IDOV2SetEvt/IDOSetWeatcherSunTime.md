### 设置日出日落时间


功能表：support_set_weatch_sun_time_0a_06(c库jsonid SDK待补充)

**Flutter示例：**

```dart
/// 设置日出日落时间事件号
setWeatherSunTime(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_weatcher_set_sun_time),

/// 设置日出日落时间
libManager.send(evt: CmdEvtType.setWeatherSunTime, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明    |
| ------------ | -------- | ----------- |
| sunrise_hour | int      | 日出时间 时 |
| sunrise_min  | int      | 日出时间 分 |
| sunset_hour  | int      | 日落时间 时 |
| sunset_min   | int      | 日落时间 分 |

`示例：`

```c
{
  "sunrise_hour":6,
  "sunrise_min":12,
  "sunset_hour":18,
  "sunset_min":30
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`

```c
{
  "is_success":1
}
```