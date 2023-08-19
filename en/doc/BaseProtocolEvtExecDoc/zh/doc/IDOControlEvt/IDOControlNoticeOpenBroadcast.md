### APP通知固件开启bt广播


**Flutter示例：**

```dart
/// app通知固件开启bt广播事件号
setNoticeOpenBroadcastn(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_notcie_open_broadcast
),

/// app通知固件开启bt广播
libManager.send(evt: CmdEvtType.setNoticeOpenBroadcastn, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                     |
| -------- | -------- | ---------------------------- |
| err_code | int      | 成功：0  <br />失败：1 |

`示例：`

```c
{
    "err_code":1
}
```
