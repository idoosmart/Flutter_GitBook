### 控制设备断线


**Flutter示例：**

```dart
/// 控制断线事件号
controlDisconnect(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_control_disconnect),

/// 控制断线
libManager.send(evt: CmdEvtType.controlDisconnect, json: jsonEncode(json));
```

