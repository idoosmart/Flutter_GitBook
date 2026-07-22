### 获取固件红点提示开关状态


功能表:TODO

**Flutter示例：**

```dart
/// 获取红点提醒开关事件号
getUnreadAppReminder(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_unread_app_onoff
),

/// 获取红点提醒开关
libManager.send(evt: CmdEvtType.getUnreadAppReminder, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明                                           |
| ------ | -------- | -------------------------------------------------- |
| on_off | int      | 开关状态  <br />1:打开 <br />0:关闭<br />-1:不支持 |

`示例：`

```c
{
    "on_off":0
}
```
