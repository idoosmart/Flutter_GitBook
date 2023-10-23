### 控制拍照停止


**Flutter示例：**

```dart
/// 结束拍照 (app -> ble)事件号
photoStop(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_photo_stop),

/// 结束拍照 (app -> ble)
libManager.send(evt: CmdEvtType.photoStop, json: jsonEncode(json));
```

