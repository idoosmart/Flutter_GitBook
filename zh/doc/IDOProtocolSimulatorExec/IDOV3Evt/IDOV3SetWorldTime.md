### V3下发世界时间


功能表:setSetV3WorldTime

**Flutter示例：**

```dart
/// v3 下发v3世界时间
setWorldTimeV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_world_time),

/// v3 下发v3世界时间
libManager.send(evt: CmdEvtType.setWorldTimeV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| version        | int      | 协议库版本号                                                 |
| items_num      | int      | 时钟个数 每次下发所有的时钟<br />最大10个                    |
| items          | 集合     | 世界时钟详情<br />id & min_offset & city_name & sunrise_hour & sunrise_min & sunset_hour & sunset_min & longitude_flag & longitude & latitude_flag & latitude的集合 |

| 字段名         | 字段类型 | 字段说明                                                  |
| -------------- | -------- | --------------------------------------------------------- |
| id             | int      | 详情id,唯一                                               |
| min_offset     | int      | 当前的时间和0时区的偏移分钟数据                           |
| city_name      | char []  | 城市名称 最大59个字节                                     |
| sunrise_hour   | int      | 日出时间 时                                               |
| sunrise_min    | int      | 日出时间 分                                               |
| sunset_hour    | int      | 日落时间 时                                               |
| sunset_min     | int      | 日落时间 分                                               |
| longitude_flag | int      | 1：东经  2：西经                                          |
| longitude      | int      | 经度 保留2位小数扩大100倍传输， app需要将对应的分转换成度 |
| latitude_flag  | int      | 1：北纬   2：南纬                                         |
| latitude       | Int      | 纬度 保留2位小数扩大100倍传输， app需要将对应的分转换成度 |

`示例：`

```c
{
  "items_num": 4,
  "items": [{
    "id": 31,
    "min_offset": 480,
    "city_name": "北京",
    "sunrise_hour": 7,
    "sunrise_min": 25,
    "sunset_hour": 16,
    "sunset_min": 49,
    "longitude_flag": 1,
    "longitude": 11641,
    "latitude_flag": 1,
    "latitude": 3990
  }, {
    "id": 295,
    "min_offset": 540,
    "city_name": "东京",
    "sunrise_hour": 6,
    "sunrise_min": 41,
    "sunset_hour": 16,
    "sunset_min": 28,
    "longitude_flag": 1,
    "longitude": 13965,
    "latitude_flag": 1,
    "latitude": 3568
  }, {
    "id": 148,
    "min_offset": 0,
    "city_name": "伦敦",
    "sunrise_hour": 7,
    "sunrise_min": 56,
    "sunset_hour": 15,
    "sunset_min": 51,
    "longitude_flag": 2,
    "longitude": 13,
    "latitude_flag": 1,
    "latitude": 5151
  }, {
    "id": 197,
    "min_offset": -300,
    "city_name": "纽约",
    "sunrise_hour": 7,
    "sunrise_min": 10,
    "sunset_hour": 16,
    "sunset_min": 28,
    "longitude_flag": 2,
    "longitude": 7401,
    "latitude_flag": 1,
    "latitude": 4071
  }]
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                  |
| -------- | -------- | ------------------------- |
| version  | int      | 协议库版本号              |
| err_code | int      | 错误码 0成功，非0是错误码 |

`示例：`

```c
{
    "version":0,
    "err_code":0
}
```

