#### 同步环境音量(噪声)


**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                     |
| ------------- | -------- | ---------------------------- |
| year          | int      | 数据日期 年                  |
| month         | int      | 数据日期 月                  |
| day           | int      | 数据日期 日                  |
| hour          | int      | 数据日期 时                  |
| minute        | int      | 数据日期 分                  |
| second        | int      | 数据日期 秒                  |
| version       | int      | 协议版本号 0              |
| start_time    | int      | 开始的同步时间 单位秒        |
| interval_mode | int      | 2个数据的间隔   单位秒       |
| avg_noise     | int      | 平均的噪音                   |
| max_noise     | int      | 最大噪音                     |
| min_noise     | int      | 最小噪音                     |
| noise_count   | int      | 噪声详情个数                 |
| items         | 集合     | 噪声详情，`offset`&`value`的集合 |

| 字段名 | 字段类型 | 字段说明   |
| ------ | -------- | ---------- |
| offset | int      | 数据的偏移 |
| value  | int      | 噪声值     |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "hour":11,
    "minute":58,
    "second":30,
    "version":0,
    "start_time":0,
    "interval_mode":30,
    "avg_noise":50,
    "max_noise":60,
    "min_noise":40,
    "noise_count":2,
    "items":[
        {
            "offset":30,
            "value":50
        },
        {
            "offset":30,
            "value":50
        }
    ]
}
```
