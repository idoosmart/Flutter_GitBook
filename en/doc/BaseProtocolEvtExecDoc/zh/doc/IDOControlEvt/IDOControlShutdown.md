### 控制关闭设备


**Flutter示例：**

```dart
/// 关闭设备事件号
shutdown(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_shutdown),

/// 关闭设备
libManager.send(evt: CmdEvtType.shutdown, json: jsonEncode(json));
```

