### 直接进入升级模式(忽略电量)


**Flutter示例：**

```dart
/// 直接进入升级模式(忽略电量)事件号
otaDirectStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_ota_direct_start),

/// 直接进入升级模式(忽略电量)
libManager.send(evt: CmdEvtType.otaDirectStart, json: jsonEncode(json));
```

