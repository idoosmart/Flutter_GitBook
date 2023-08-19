### 控制设备重启


**Flutter示例：**

```dart
/// 重启设备事件号
reboot(evtBase: _VBusEvtBase.base_app_set,
       evtType: _VBusEvtType.app_reboot),

/// 重启设备
libManager.send(evt: CmdEvtType.reboot, json: jsonEncode(json));
```

