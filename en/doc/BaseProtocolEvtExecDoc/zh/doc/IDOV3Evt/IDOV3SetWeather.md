### V3设置天气数据


功能表:setSetV3Weather

**Flutter示例：**

```dart
/// v3 下发v3天气协议事件号
setWeatherV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_v3_weather),

/// v3 下发v3天气协议
libManager.send(evt: CmdEvtType.setWeatherV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名                    | 字段类型 | 字段说明                                                     |
| ------------------------- | -------- | ------------------------------------------------------------ |
| version                   | int      | 协议库版本号                                                 |
| month                     | int      | 服务器最新一次同步的月                                       |
| day                       | int      | 服务器最后一次同步的日                                       |
| hour                      | int      | 服务器最后一次同步的时                                       |
| min                       | int      | 服务器最后一次同步的分                                       |
| sec                       | int      | 服务器最后一次同步的秒                                       |
| week                      | int      | 当前是星期几<br />bit0：星期1<br />bit1：星期2<br />类推到星期天 |
| weather_type              | int      | 天气类型<br />0：其他<br />1：晴<br />2：多云<br />3：阴<br />4：雨<br />5：暴雨<br />6：雷阵雨<br />7：雪<br />8：雨夹雪<br />9：台风<br />10：沙尘暴<br />11：夜间晴<br />12：夜间多云<br />13：热<br />14：冷<br />15：清风<br />16：大风<br />17：雾霭<br />18：阵雨<br />19：多云转晴  <br />48：雷  <br />49：冰雹  <br />50：扬沙  <br />51：龙卷风(realme定制天气类型idw02) |
| today_tmp                 | int      | 当前的温度<br />单位摄氏度<br />适配负数，温度加100传输      |
| today_max_temp            | int      | 最大温度<br />单位摄氏度<br />适配负数，温度加100传输        |
| today_min_temp            | int      | 最小温度<br />单位摄氏度<br />适配负数，温度加100传输        |
| city_name                 | char []   | 城市名称<br />最大75个字节                                   |
| air_quality               | int      | 空气质量<br />扩大10倍传输                                   |
| precipitation_probability | int      | 降水概率<br />0-100 百分比                                   |
| humidity                  | int      | 湿度                                                         |
| today_uv_intensity        | int      | 紫外线强度<br />扩大10倍传输                                 |
| wind_speed                | int      | 风速                                                         |
| sunrise_hour              | int      | 日出时间 时<br />version为1有效                              |
| sunrise_min               | int      | 日出时间 分<br />version为1有效                              |
| sunset_hour               | int      | 日出时间 时<br />version为1有效                              |
| sunset_min                | int      | 日出时间 分<br />version为1有效                              |
| sunrise_item_num | int | 日出日落时间详情个数<br />天数目前最大暂定为7天<br />version为1无效 |
| air_grade_item            | char [] | 空气质量等级内容<br />version为1无效                         |
| hours_weather_items | 集合 | 未来48小时的天气数据集合<br />weather_type & temperature & probability的集合 |
| future_items | 集合 | 未来七天的天气数据<br />weather_type & max_temp & min_temp的集合 |
| sunrise_item | 集合 | 日出日落时间详情<br />sunrise_hour & sunrise_min & sunset_hour & sunset_min的集合<br />version为1无效 |

| 字段名       | 字段类型 | 字段说明                          |
| ------------ | -------- | --------------------------------- |
| weather_type | int      | 天气类型                          |
| temperature  | int      | 温度<br />适配负数，温度加100传输 |
| probability  | int      | 温度出现的概率<br />0-100 百分比  |

| 字段名       | 字段类型 | 字段说明                              |
| ------------ | -------- | ------------------------------------- |
| weather_type | int      | 天气类型                              |
| max_temp     | int      | 最大温度<br />适配负数，温度加100传输 |
| min_temp     | int      | 最小温度<br />适配负数，温度加100传输 |

| 字段名       | 字段类型 | 字段说明                        |
| ------------ | -------- | ------------------------------- |
| sunrise_hour | int      | 日出时间 时<br />version为1无效 |
| sunrise_min  | int      | 日出时间 分<br />version为1无效 |
| sunset_hour  | int      | 日落时间 时<br />version为1无效 |
| sunset_min   | int      | 日落时间 分<br />version为1无效 |

`示例：`

```c
{
    "version":0,
    "month":12,
    "day":26,
    "hour":16,
    "min":31,
    "sec":30,
    "week":1,
    "weather_type":1,
    "today_tmp":21,
    "today_max_temp":23,
    "today_min_temp":12,
    "city_name":"shenzhen",
    "air_quality":53,
    "precipitation_probability":1,
    "humidity":0,
    "today_uv_intensity":0,
    "wind_speed":0,
    "sunrise_hour":6,
    "sunrise_min":20,
    "sunset_hour":18,
    "sunset_min":17,
    "sunrise_item_num":0,
    "air_grade_item":[],
    "hours_weather_items":[
        {
            "weather_type":1,
            "temperature":0,
            "probability":0
        },
        {
            "weather_type":1,
            "temperature":0,
            "probability":0
        }
    ],
    "future_items":null,
    "sunrise_item":null
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

