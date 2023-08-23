### Set Unbinding (Internal Use)


**Flutter Example:**

```dart
/// Event number for unbinding
setBindRemove(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_bind_remove),

/// Unbind
libManager.send(evt: CmdEvtType.setBindRemove, json: jsonEncode(json));
```
