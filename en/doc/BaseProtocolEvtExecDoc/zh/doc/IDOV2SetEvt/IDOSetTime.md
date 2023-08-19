### 设置时间


**Flutter示例：**

```dart
/// 设置时间
setTime(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_time),

/// 设置时间
libManager.send(evt: CmdEvtType.setTime, json: jsonEncode(json));
```

**App下发的json字段**：

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| year      | int      | 年                                                           |
| monuth    | int      | 月                                                           |
| day       | int      | 日                                                           |
| hour      | int      | 时                                                           |
| minute    | int      | 分                                                           |
| second    | int      | 秒                                                           |
| week      | int      | 星期<br />0~6， 表示星期一到星期天                           |
| time_zone | int      | 用24时区的，手机端的获取时区是整数<br />0-12东，13-24西,需要功能表支持 |

`示例：`

```c
{
  "year":2022,
  "monuth":12,
  "day":16,
  "hour":17,
  "minute":49,
  "second":46,
  "week":5,
  "time_zone":8
}
```

