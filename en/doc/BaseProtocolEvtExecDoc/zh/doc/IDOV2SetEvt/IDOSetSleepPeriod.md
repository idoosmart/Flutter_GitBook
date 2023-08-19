### 设置睡眠时间段


功能表：exSleepPeriod

**Flutter示例：**

```dart
/// 设置睡眠时间段事件号
setSleepPeriod(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_sleep_period),

/// 设置睡眠时间段
libManager.send(evt: CmdEvtType.setSleepPeriod, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                   |
| ------------ | -------- | -------------------------- |
| on_off       | int      | 开关<br />170 开 85是关 |
| start_hour   | int      | 开始时间 时                |
| start_minute | int      | 开始时间 分                |
| end_hour     | int      | 结束时间 时                |
| end_minute   | int      | 结束时间 分                |

`示例：`

```c
{
  "on_off":170,
  "start_hour":23,
  "start_minute":0,
  "end_hour":8,
  "end_minute":0
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

