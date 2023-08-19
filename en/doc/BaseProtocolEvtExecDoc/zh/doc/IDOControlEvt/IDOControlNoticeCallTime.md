### 下发通话时间给固件


**Flutter示例：**

```dart
/// 来电接通完成后下发通话时间给固件事件号
setNoticeCallTime(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_notice_call_time),

/// 来电接通完成后下发通话时间给固件
libManager.send(evt: CmdEvtType.setNoticeCallTime, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明        |
| ------ | -------- | --------------- |
| sec    | int      | 通话时间 单位秒 |

`示例：`

```c
{
    "sec":30
}
```

**App收到的json字段**：

| 字段名       | 字段类型 | 字段说明                              |
| ------------ | -------- | ------------------------------------- |
| status\_code | int      | 0：成功<br />1：失败 参数不正确 |

`示例：`

```c
{
    "status_code":0
}
```
