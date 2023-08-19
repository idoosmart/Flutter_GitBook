### 控制拍照开始


**Flutter示例：**

```dart
/// 开始拍照 (app -> ble)事件号
photoStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_photo_start),

/// 开始拍照 (app -> ble)
libManager.send(evt: CmdEvtType.photoStart, json: jsonEncode(json));
```

