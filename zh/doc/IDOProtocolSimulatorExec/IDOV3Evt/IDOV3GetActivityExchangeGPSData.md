### V3多运动数据数据交换中获取一段时间的GPS数据


**Flutter示例：**

```dart
/// v3多运动数据数据交换中获取一段时间的gps数据事件号
getActivityExchangeGpsData(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_activity_exchange_gps_data),

/// v3多运动数据数据交换中获取一段时间的gps数据
libManager.send(evt: CmdEvtType.getActivityExchangeGpsData, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明                                        |
| --------------- | -------- | ----------------------------------------------- |
| version         | int      | 协议版本号                                      |
| hour            | int      | 时                                              |
| minute          | int      | 分                                              |
| second          | int      | 秒                                              |
| interval_second | int      | 间隔时间 <br />单位秒                           |
| GPS_data_len    | int      | gps数据长度                                     |
| GPS_data        | 集合     | gps数据详情集合<br />latitude & longitude的集合 |

| 字段名    | 字段类型 | 字段说明 |
| --------- | -------- | -------- |
| latitude  | double   | 经度     |
| longitude | double   | 纬度     |

`示例：`

```c
{
    "version":0,
    "hour":0,
    "minute":0,
    "second":0,
    "interval_second":0,
    "GPS_data_len":1,
    "GPS_data":[
        {
            "latitude":0,
            "longitude":0
        }
    ]
}
```

