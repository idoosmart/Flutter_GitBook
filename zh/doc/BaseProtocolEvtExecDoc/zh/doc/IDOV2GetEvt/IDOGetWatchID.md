### ~~获取表盘ID~~


功能表:getWatchID

**Flutter示例：**

```dart
/// 获取表盘id事件号
getWatchDialId(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_watch_id),

/// 获取表盘id
libManager.send(evt: CmdEvtType.getWatchDialId, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明 |
| -------- | -------- | -------- |
| watch_id | int      | 表盘id   |

`示例：`

```c
{
  "watch_id":1
}
```

