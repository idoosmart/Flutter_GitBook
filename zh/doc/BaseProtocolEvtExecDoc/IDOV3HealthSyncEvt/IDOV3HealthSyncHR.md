#### 同步心率


**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| year              | int      | 数据日期 年                                                  |
| month             | int      | 数据日期 月                                                  |
| day               | int      | 数据日期 日                                                  |
| start_time        | int      | 开始时间,单位秒,距离0点的偏移                                |
| data_type         | int      | ~~0为无效,1为一个值,2为最大和最小值~~ (预留字段)             |
| silent_hr         | int      | 静息心率                                                     |
| five_min_max_data | int      | 五分钟心率最大值                                             |
| five_min_min_data | int      | 五分钟心率最小值                                             |
| five_min_avg_data | int      | 五分钟心率平均值                                             |
| five_min_data     | int []   | 五分钟心率全部心率值                                         |
| hr_data_count     | int      | 过高过低时的心率数据个数 <br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |
| hr_interval       | 集合     | 5个心率区间:热身心率区间 极限心率区间 燃脂心率区间 有氧耐力心率区间 无氧耐力心率区间<br />`threshold` & `minute`的集合 |
| items             | 集合     | 心率数据 `offset` & `heart_rateVal`的集合                    |
| hr_data           | 集合     | 心率过高过低数据 `hour` & `minute` & `type` & `heart_rate` 的集合<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |

| 字段名        | 字段类型 | 字段说明    |
| ------------- | -------- | ----------- |
| offset        | int      | 偏移 单位秒 |
| heart_rateVal | int      | 心率值      |

| 字段名    | 字段类型 | 字段说明 |
| --------- | -------- | -------- |
| threshold | int      | 阀值     |
| minute    | int      | 分钟     |

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| hour       | int      | 过高过低时的心率数据时间 时<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |
| minute     | int      | 过高过低时的心率数据时间 分<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |
| type       | int      | 心率值类型 <br />0：心率过低时的心率值 <br />1：心率过高时的心率值<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |
| heart_rate | int      | 心率值 单位：次/分<br />`v3SupportSyncOverHighLowHeartData`功能表未开启的时候返回0 |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "data_type":0,
    "silent_hr":85,
    "five_min_max_data":0,
    "five_min_min_data":0,
    "five_min_avg_data":0,
    "hr_data_count":2,
    "five_min_data":[
        85,
        90,
        80,
        83
    ],
    "hr_interval":[
        {
            "threshold": 80,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        }
    ],
    "items":[
        {
            "offset":80,
            "heart_rateVal":5
        },
        {
            "offset":83,
            "heart_rateVal":5
        }
    ],
    "hr_data":[
        {
            "hour":11,
            "minute":25,
            "type":1,
            "heart_rate":120
        },
        {
            "hour":11,
            "minute":25,
            "type":0,
            "heart_rate":70
        }
    ]
}
```
