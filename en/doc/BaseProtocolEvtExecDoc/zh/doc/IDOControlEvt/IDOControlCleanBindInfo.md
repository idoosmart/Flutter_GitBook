### 清除绑定信息


**Flutter示例：**

```dart
/// 清除绑定信息事件号
cleanBindInfo(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_clean_bond_info),

/// 清除绑定信息
libManager.send(evt: CmdEvtType.cleanBindInfo, json: jsonEncode(json));
```

