### 获取HID信息


功能表 /// TODO

**Flutter示例：**

```dart
/// 获取hid信息事件号
getHidInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_hid_info),

/// 获取hid信息
libManager.send(evt: CmdEvtType.getHidInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                 |
| -------- | -------- | ------------------------ |
| is_start | int      | 0没有启动<br />1启动成功 |

`示例：`

```c
{
  "is_start" : 0
}
```
