### 控制寻找设备停止


**Flutter示例：**

```dart
/// 结束寻找设备 (app -> ble)事件号
findDeviceStop(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_find_device_stop),

/// 结束寻找设备 (app -> ble)
libManager.send(evt: CmdEvtType.findDeviceStop, json: jsonEncode(json));
```
