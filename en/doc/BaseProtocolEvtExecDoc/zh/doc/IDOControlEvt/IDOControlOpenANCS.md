### 控制打开ancs开始


**Flutter示例：**

```dart
/// 打开ancs事件号
openAncs(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_open_ancs),

/// 打开ancs
libManager.send(evt: CmdEvtType.openAncs, json: jsonEncode(json));
```

