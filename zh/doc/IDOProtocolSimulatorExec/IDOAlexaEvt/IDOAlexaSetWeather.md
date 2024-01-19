### V3AlEXA设置天气


功能表:alexaSetWeatherV3

**App下发的json字段**:

| 字段名                | 字段类型 | 字段说明                                                     |
| --------------------- | -------- | ------------------------------------------------------------ |
| version               | int      | 协议库版本号                                                 |
| cur_weather           | char []  | 当前温度 <br />最大值8个字节                                 |
| location              | char []  | 地方 <br />最大值80个字节                                    |
| today_weather_state   | char []  | 天气情况 <br />最大值30个字节                                |
| today_min_max_weather | char []  | 最大最小温度字符串<br />最大值20个字节                       |
| future_weather_len    | int      | 天气详情个数                                                 |
| future_weather        | 集合     | 未来天气详情集合, <br />date & weather_state & min_max_weather的集合 |

| 字段名          | 字段类型 | 字段说明                               |
| --------------- | -------- | -------------------------------------- |
| date            | char []  | 日期字符串<br />最大值20个字节         |
| weather_state   | char []  | 天气情况<br />最大值30个字节           |
| min_max_weather | char []  | 最大最小温度字符串<br />最大值20个字节 |


`示例：`

```c
{
    "version":0,
    "cur_weather":"",
    "location":"shenzhen",
    "today_weather_state":"",
    "today_min_max_weather":"",
    "future_weather_len":1,
    "future_weather":[
        {
            "date":"",
            "weather_state":"",
            "min_max_weather":""
        }
    ]
}
```

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明     |
| ---------- | -------- | ------------ |
| is_success | int      | 1成功  0失败 |

`示例：`

```c
{
    "is_success":1
}
```

