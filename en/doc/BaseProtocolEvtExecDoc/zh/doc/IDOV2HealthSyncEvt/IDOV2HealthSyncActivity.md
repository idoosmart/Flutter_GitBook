#### 同步活动(多运动)数据


**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
|        |          |          |

**App收到的json字段**：

| 字段名                  | 字段类型 | 字段说明                        |
| ----------------------- | -------- | ------------------------------- |
| year                    | int      | 年                              |
| month                   | int      | 月                              |
| day                     | int      | 日                              |
| hour                    | int      | 时                              |
| minute                  | int      | 分                              |
| second                  | int      | 秒                              |
| data_length             | int      | 数据长度                        |
| hr_data_interval_minute | int      | 心率数据间隔                    |
| hr_item_count           | int      | 心率个数                        |
| packet_count            | int      | 包数量统计                      |
| type                    | int      | 运动类型                        |
| step                    | int      | 步数/个数                       |
| durations               | int      | 时长                            |
| calories                | int      | 卡路里                          |
| distance                | int      | 距离                            |
| avg_hr_value            | int      | 平均心率                        |
| max_hr_value            | int      | 最大心率                        |
| burn_fat_mins           | int      | 脂肪燃烧时间                    |
| aerobic_mins            | int      | 有氧运动时间                    |
| limit_mins              | int      | 极限锻炼时间                    |
| range1                  | int      | 热身运动的累积时长 单位分钟     |
| range2                  | int      | 脂肪燃烧的累积时长 单位分钟     |
| range3                  | int      | 有氧运动的累积时长 单位分钟     |
| range4                  | int      | 无氧运动的累积时长 单位分钟     |
| range5                  | int      | 极限锻炼的累积时长 单位分钟     |
| hr_data_vlaue           | int []   | 心率数据详情<br />最大个数68535 |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "hour":10,
    "minute":38,
    "second":20,
    "data_length":10,
    "hr_data_interval_minute":5,
    "hr_item_count":10,
    "packet_count":1,
    "type":1,
    "step":200,
    "durations":10,
    "calories":50,
    "distance":200,
    "avg_hr_value":85,
    "max_hr_value":90,
    "burn_fat_mins":0,
    "aerobic_mins":0,
    "limit_mins":0,
    "range1":0,
    "range2":0,
    "range3":0,
    "range4":0,
    "range5":0,
    "hr_data_vlaue":[
        85,
        87,
        90,
        93,
        91,
        80,
        90,
        81,
        83,
        86
    ],
}
```

