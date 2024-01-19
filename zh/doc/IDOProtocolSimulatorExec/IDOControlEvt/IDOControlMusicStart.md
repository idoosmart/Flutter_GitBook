### 控制音乐开始


**Flutter示例：**

```dart
/// 控制音乐开始事件号
musicStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_music_start),

/// 控制音乐开始
libManager.send(evt: CmdEvtType.musicStart, json: jsonEncode(json));
```

