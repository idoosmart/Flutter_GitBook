### 控制打开ancs停止


**Flutter示例：**

```dart
/// 关闭ancs事件号
closeAncs(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_close_ancs),

/// 关闭ancs
libManager.send(evt: CmdEvtType.closeAncs, json: jsonEncode(json));
```

