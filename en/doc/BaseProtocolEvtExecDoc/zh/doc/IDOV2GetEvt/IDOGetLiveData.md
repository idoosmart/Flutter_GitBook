### 获得实时数据


功能表:getRealtimeData

**Flutter示例：**

```dart
/// 获得实时数据事件号
getLiveData(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_live_data),

/// 获得实时数据
libManager.send(evt: CmdEvtType.getLiveData, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| flag   | int      | 0：无功能<br />1：强制打开心率监测<br />2：强制打开血压监测 |

**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                             |
| ----------------- | -------- | ---------------------------------------------------- |
| total_step        | int      | 总步数                                               |
| total_calories    | int      | 总卡路里 <br />单位大卡                              |
| total_distances   | int      | 总距离 <br />单位m                                   |
| total_active_time | int      | 总活动时长<br />单位秒                               |
| heart_rate        | int      | 心率数据<br />单位bpm<br />如果没有心率功能，该值为0 |

`示例：`

```c
{
  "heart_rate" : 0,
  "total_active_time" : 0,
  "total_calories" : 0,
  "total_distances" : 0,
  "total_step" : 0
}
```

