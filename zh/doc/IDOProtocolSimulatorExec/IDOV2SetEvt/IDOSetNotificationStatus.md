### 设置通知应用状态


功能表：setSetNotificationStatus

**Flutter示例：**

```dart
/// 目前只适配事项提醒，所以这个接口目前默认设置的是事项提醒的通知类型
/// 通知应用状态设置事件号
setNotificationStatus(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_notification_status),

/// 手机app通过这个命令开关，实现事项提醒的通知类型设置
libManager.send(evt: CmdEvtType.setNotificationStatus, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名      | 字段类型 | 字段说明                                                     |
| ----------- | -------- | ------------------------------------------------------------ |
| notify_flag | int      | 通知类型：<br />1：允许通知 <br />2：静默通知   <br />3：关闭通知 |

`示例：`

```c
{
  "notify_flag":1
}
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明             |
| ---------- | -------- | -------------------- |
| is_success | int      | 0是失败<br />1是成功 |

`示例：`
```c
{
  "is_success":0
}
```
