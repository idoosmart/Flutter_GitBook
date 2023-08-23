### V3ALEXA获取闹钟


功能表:alexaSetGetAlexaAlarmV3

**App收到的json字段**：

| 字段名  | 字段类型 | 字段说明                                                     |
| ------- | -------- | ------------------------------------------------------------ |
| version | int      | 协议版本号                                                   |
| item    | 集合     | 闹钟详情集合，alarm_id & status & year & month & day & hour & minute & repeat的集合 |

| 字段名   | 字段类型 | 字段说明                                           |
| -------- | -------- | -------------------------------------------------- |
| alarm_id | int      | 闹钟id                                             |
| status   | int      | 170不显示(删除) 85显示                             |
| year     | int      | 年                                                 |
| month    | int      | 月                                                 |
| day      | int      | 日                                                 |
| hour     | int      | 时                                                 |
| minute   | int      | 分                                                 |
| repeat   | int      | 重复 bit1-bit7 周一到周日  bit 0是总开关位（开关） |

`示例：`

```c
{
    "version":0,
    "item":[
        {
            "alarm_id":1,
            "status":85,
            "year":2022,
            "month":12,
            "day":26,
            "hour":14,
            "minute":54,
            "repeat":127
        },
        {
            "alarm_id":2,
            "status":170,
            "year":2022,
            "month":12,
            "day":26,
            "hour":15,
            "minute":54,
            "repeat":127
        },
        {
            "alarm_id":3,
            "status":170,
            "year":2022,
            "month":12,
            "day":26,
            "hour":16,
            "minute":54,
            "repeat":127
        },
        {
            "alarm_id":4,
            "status":170,
            "year":2022,
            "month":12,
            "day":26,
            "hour":20,
            "minute":54,
            "repeat":127
        },
        {
            "alarm_id":5,
            "status":170,
            "year":2022,
            "month":12,
            "day":26,
            "hour":22,
            "minute":54,
            "repeat":127
        },
        {
            "alarm_id":6,
            "status":170,
            "year":2022,
            "month":12,
            "day":26,
            "hour":23,
            "minute":0,
            "repeat":127
        },
        {
            "alarm_id":7,
            "status":170,
            "year":2022,
            "month":12,
            "day":27,
            "hour":8,
            "minute":00,
            "repeat":127
        },
        {
            "alarm_id":8,
            "status":170,
            "year":2022,
            "month":12,
            "day":27,
            "hour":14,
            "minute":0,
            "repeat":127
        },
        {
            "alarm_id":9,
            "status":170,
            "year":2022,
            "month":12,
            "day":27,
            "hour":15,
            "minute":20,
            "repeat":127
        },
        {
            "alarm_id":10,
            "status":170,
            "year":2022,
            "month":12,
            "day":27,
            "hour":15,
            "minute":30,
            "repeat":127
        }
    ]
}
```

