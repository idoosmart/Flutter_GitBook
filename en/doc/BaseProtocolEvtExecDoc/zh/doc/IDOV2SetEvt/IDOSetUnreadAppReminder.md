### 设置未读信息红点提示开关


功能表：setSetUnreadAppReminder

**Flutter示例：**

```dart
/// 未读信息红点提示开关事件号
setUnreadAppReminder(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_unread_app_reminder),

/// 未读信息红点提示开关
libManager.send(evt: CmdEvtType.setUnreadAppReminder, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                              |
| ------ | -------- | ------------------------------------- |
| on_off | int      | 开关<br />170：打开 <br />85：关闭 |

`示例：`

```c
{
  "on_off":85
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
