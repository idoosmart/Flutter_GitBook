### 控制寻找设备开始


**Flutter示例：**

```dart
/// 寻找设备开始 (app -> ble)事件号
findDeviceStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_find_device_start),

/// 寻找设备开始 (app -> ble)
libManager.send(evt: CmdEvtType.findDeviceStart, json: jsonEncode(json));
```

