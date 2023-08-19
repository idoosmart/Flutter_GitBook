#### 同步心率数据


**App收到的json字段**：

| 字段名              | 字段类型 | 字段说明                                               |
| ------------------- | -------- | ------------------------------------------------------ |
| year                | int      | 数据日期 年                                            |
| month               | int      | 数据日期 月                                            |
| day                 | int      | 数据日期 日                                            |
| start_time          | int      | 数据距离0点的偏移 单位分钟                             |
| silent_heart_rate   | int      | 静息心率                                               |
| burn_fat_threshold  | int      | 心率区间的阈值，脂肪燃烧                               |
| aerobic_threshold   | int      | 心率区间的阈值，有氧运动                               |
| limit_threshold     | int      | 心率区间的阈值，极限运动                               |
| burn_fat_mins       | int      | 脂肪燃烧的心率持续时间，单位分钟                       |
| aerobic_mins        | int      | 有氧运动的持续时间                                     |
| limit_mins          | int      | 极限锻炼的持续时间                                     |
| warm_up_threshold   | int      | 心率区间的阈值，热身运动                               |
| warm_up_mins        | int      | 热身运动的持续时间                                     |
| anaerobic_threshold | int      | 心率区间的阈值，无氧运动                               |
| anaerobic_mins      | int      | 无氧运动的持续时间                                     |
| items               | 集合     | 心率的详情<br />offset_minute & heart_rave_value的集合 |

| 字段名           | 字段类型 | 字段说明                                 |
| ---------------- | -------- | ---------------------------------------- |
| offset_minute    | int      | 数据的偏移，单位分钟，用于定位数据的时间 |
| heart_rave_value | int      | 心率值                                   |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":23,
    "start_time":0,
    "silent_heart_rate":80,
    "burn_fat_threshold":0,
    "aerobic_threshold":0,
    "limit_threshold":0,
    "burn_fat_mins":0,
    "aerobic_mins":0,
    "limit_mins":0,
    "warm_up_threshold":0,
    "warm_up_mins":0,
    "anaerobic_threshold":0,
    "anaerobic_mins":0,
    "items":[
        {
            "offset_minute":5,
            "heart_rave_value":90
        },
        {
            "offset_minute":5,
            "heart_rave_value":80
        },
        {
            "offset_minute":5,
            "heart_rave_value":85
        }
    ]
}
```
