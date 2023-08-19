### 设置久坐提醒


功能表: setSedentariness

**Flutter示例：**

```dart
/// 设置久坐事件号
setLongSit(
  evtBase: _VBusEvtBase.base_app_set, 
  evtType: _VBusEvtType.app_set_long_sit),

/// 设置久坐
libManager.send(evt: CmdEvtType.setLongSit, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| start_hour   | int      | 开始时间 时                                                  |
| start_minute | int      | 开始时间 分                                                  |
| end_hour     | int      | 结束时间 时                                                  |
| end_minute   | int      | 结束时间 分                                                  |
| interval     | int      | 间隔 <br />取值应大于15分钟 单位分钟                         |
| repetitions  | int      | 重复及开关<br /> bit0 ：0表示关 1表示开 <br />bit1-7  : 0表示不重复，1表示重复 |

`示例：`

```c
{
  "start_hour":15,
  "start_minute":40,
  "end_hour":23,
  "end_minute":26,
  "interval":15,
  "repetitions":254
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



