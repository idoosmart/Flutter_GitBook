### 设置解绑(内部使用)


**Flutter示例：**

```dart
/// 解绑事件号
setBindRemove(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_bind_remove),

/// 解绑
libManager.send(evt: CmdEvtType.setBindRemove, json: jsonEncode(json));
```
