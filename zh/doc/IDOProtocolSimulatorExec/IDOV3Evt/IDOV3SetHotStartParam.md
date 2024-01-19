### V3设置GPS热启动参数


**Flutter示例：**

```dart
/// v3设置gps热启动参数事件号
setHotStartParamV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_hot_start_param),

/// v3设置gps热启动参数
libManager.send(evt: CmdEvtType.setHotStartParamV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名      | 字段类型 | 字段说明               |
| ----------- | -------- | ---------------------- |
| accmaj      | int      | 参考高度 单位米        |
| accmin      | int      | 半主要RMS精度 单位米   |
| accvert     | int      | 方向角 单位度          |
| altitude    | int      | 高度 x10               |
| bear        | int      | 半次要RMS精度 单位米   |
| latitude    | int      | 纬度 x10^6  北纬为正数 |
| longitude   | int      | 经度 x10^6  东经为正数 |
| tcxo_offset | int      | 晶振偏移               |

`示例：`

```c
{
    "accmaj":0,
    "accmin":0,
    "accvert":0,
    "altitude":0,
    "bear":0,
    "latitude":0,
    "longitude":0,
    "tcxo_offset":0
}
```
