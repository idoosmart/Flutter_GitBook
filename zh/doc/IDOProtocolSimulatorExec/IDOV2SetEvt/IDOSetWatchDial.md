### 设置表盘

功能表：WatchDial

**Flutter示例：**

```dart
/// 设置表盘事件号
setWatchDial(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_watch_dial),

/// 设置表盘
libManager.send(evt: CmdEvtType.setWatchDial, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名  | 字段类型 | 字段说明                                               |
| ------- | -------- | ------------------------------------------------------ |
| dial_id | int      | 设置的手环本地表盘<br />表盘id<br />0无效,目前支持1\~4 |

`示例：`

```c
{
  "dial_id":1
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明           |
| -------- | -------- | ------------------ |
| ret_code | int      | 0 成功，非0失败 |

`示例：`

```c
{
  "ret_code":0
}
```
