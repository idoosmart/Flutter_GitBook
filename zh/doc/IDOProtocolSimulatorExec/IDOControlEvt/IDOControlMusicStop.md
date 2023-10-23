### 控制音乐停止


**Flutter示例：**

```dart
/// 控制音乐停止事件号
musicStop(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_music_stop),

/// 控制音乐停止
libManager.send(evt: CmdEvtType.musicStop, json: jsonEncode(json));
```

