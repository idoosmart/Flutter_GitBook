#### 同步运动数据


**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| year              | int      | 数据日期 年                                                  |
| month             | int      | 数据日期 月                                                  |
| day               | int      | 数据日期 日                                                  |
| total_step        | int      | 当天总步数                                                   |
| total_cal         | int      | 当天总卡路里                                                 |
| total_distances   | int      | 当天总距离                                                   |
| total_active_time | int      | 当天总活跃时长                                               |
| minute_offset     | int      | 数据的距离0点的开始时间，单位分钟                            |
| per_minute        | int      | 数据的间隔时间 单位分钟， 一般是15分钟                       |
| keyword           | int      | 预留                                                             |
| items             | 集合     | 运动详情<br />sport_count & active_time & calories & distance的集合 |

| 字段名      | 字段类型 | 字段说明          |
| ----------- | -------- | ----------------- |
| sport_count | int      | 步数              |
| active_time | int      | 运动数据 单位分钟 |
| calories    | int      | 卡路里            |
| distance    | int      | 距离 单位米       |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":23,
    "total_step":20,
    "total_cal":200,
    "total_distances":500,
    "total_active_time":6,
    "minute_offset":0,
    "per_minute":15,
    "keyword":0,
    "items":[
        {
            "sport_count":2,
            "active_time":2,
            "calories":50,
            "distance":100,
        },
        {
            "sport_count":8,
            "active_time":2,
            "calories":50,
            "distance":200,
        },
        {
            "sport_count":10,
            "active_time":2,
            "calories":100,
            "distance":200,
        }
    ]
}
```
