### 设置音乐开关


功能表: setBleControlMusic 【supportV2SetShowMusicInfoSwitch(SDK待补充)】

**Flutter示例：**

```dart
/// 设置音乐开关事件号
setMusicOnOff(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_muisc_onoff),

/// 设置音乐开关
libManager.send(evt: CmdEvtType.setMusicOnOff, json: jsonEncode(json));
```

**App下发的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| on_off           | int      | 开关<br />170 开 <br />85 关                              |
| show_info_status | int      | 展示歌曲信息开关<br />170:开 85:关<br />需要固件开启功能表支持 key：support_v2_set_show_music_info_switch |

`示例：`

```c
{
  "on_off":85,
  "phone_type":85
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

