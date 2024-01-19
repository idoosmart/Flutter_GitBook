### V3设置多个走动提醒的时间点


功能表:setWalkReminderTimeGoal

**Flutter示例：**

```dart
/// 设置多个走动提醒的时间点事件号
setWalkRemindTimes(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_walk_remind_times),

/// 设置多个走动提醒的时间点
libManager.send(evt: CmdEvtType.setWalkRemindTimes, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名  | 字段类型 | 字段说明                           |
| ------- | -------- | ---------------------------------- |
| verison | int      | 协议库版本号                       |
| on_off  | int      | 开关<br />1：开<br />0：关 |
| num     | int      | items个数，即设置时间点个数        |
| items   | 集合     | 走动提醒详情<br />`hour` &` min`的集合 |

| 字段名 | 字段类型 | 字段说明        |
| ------ | -------- | --------------- |
| hour   | int      | 走动提醒时间 时 |
| min    | int      | 走动提醒时间 分 |

`示例：`

```c
{
  "version": 0,
  "on_off":1,
  "num":2,
  "items":[
      {
          "hour":8,
            "min":0
      },
      {
            "hour":12,
            "min":30
        }
  ]
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明              |
| -------- | -------- | --------------------- |
| version  | int      | 协议版本号            |
| err_code | int      | 错误码 0成功，非0失败 |

`示例：`

```c
{
  "version": 0,
  "err_code":0
}
```

