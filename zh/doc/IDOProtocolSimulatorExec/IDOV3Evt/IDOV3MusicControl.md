### V3控制音乐


功能表:setBleControlMusic 【v3MusicControl02AddSingerName】

**Flutter示例：**

```dart
/// 控制音乐事件号
musicControl(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_music_control),

/// 控制音乐
libManager.send(evt: CmdEvtType.musicControl, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| status            | int      | 状态<br />0：无效<br />1：播放<br />2：暂停<br />3：停止     |
| cur_time_second   | int      | 当前播放时间<br />单位秒                                     |
| total_time_second | int      | 总时间<br />单位秒                                           |
| music_name        | char []  | 音乐名称 最大值63个字节                                      |
| singer_name       | char []  | 歌手名称 最大值63个字节<br />固件未开启`v3MusicControl02AddSingerName`设置该值无效 |

`示例：`

```json
{
    "status":1,
    "cur_time_second":5,
    "total_time_second":360,
    "music_name":"夕阳无限好.mp3",
    "singer_name":"eason"
}
```

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明         |
| ------ | -------- | ---------------- |
| status | int      | 1：成功，0：失败 |

`示例：`

```c
{
    "status":1
}
```
