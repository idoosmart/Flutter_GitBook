#### 同步睡眠数据


**App收到的json字段**：

| 字段名             | 字段类型 | 字段说明                                     |
| ------------------ | -------- | -------------------------------------------- |
| year               | int      | 数据日期 年                                  |
| month              | int      | 数据日期 月                                  |
| day                | int      | 数据日期 日                                  |
| end_time_hour      | int      | 睡眠结束时间 时                              |
| end_time_minute    | int      | 睡眠结束时间 分                              |
| total_minute       | int      | 总时间 单位分                                |
| light_sleep_count  | int      | 浅睡眠个数                                   |
| deep_sleep_count   | int      | 深睡眠个数                                   |
| wake_count         | int      | 清醒次数                                     |
| ligth_sleep_minute | int      | 浅睡时间 单位分钟                            |
| deep_sleep_minute  | int      | 深睡时间 单位分钟                            |
| sleep_score        | int      | 睡眠分数                                     |
| items              | 集合     | 睡眠详情<br />durations & sleep_status的集合 |

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| durations    | int      | 持续时间 单位分钟                                            |
| sleep_status | int      | 睡眠状态<br />1：醒着<br />2：浅睡<br />3：深睡 <br />4：眼动 |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":23,
    "end_time_hour":20,
    "end_time_minute":0,
    "total_minute":30,
    "light_sleep_count":3,
    "deep_sleep_count":1,
    "wake_count":1,
    "ligth_sleep_minute":22,
    "deep_sleep_minute":8,
    "sleep_score":75,
    "items":[
        {
            "durations":5,
            "sleep_status":1
        },
        {
            "durations":10,
            "sleep_status":2
        },
        {
            "durations":10,
            "sleep_status":2
        },
        {
            "durations":2,
            "sleep_status":2
        },
        {
            "durations":8,
            "sleep_status":3
        }
    ]
}
```
