### V3语音设置闹钟


**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                                                    |
| ------ | -------- | ----------------------------------------------------------- |
| item   | 集合     | alarm_id & status & year & month & day & hour &minute的集合 |

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| alarm_id | int      | 闹钟id  1-10                                                 |
| status   | int      | 开关状态<br />170关闭 85打开                                 |
| year     | int      | 年                                                           |
| month    | int      | 月                                                           |
| day      | int      | 日                                                           |
| hour     | int      | 时                                                           |
| minute   | Int      | 分                                                           |
| repeat   | int      | 重复 <br />bit1-bit7 周一到周日 bit 0是总开关位（开关）<br />需要功能表支持 key：V3_alexa_set_get_alexa_alarm |

`示例：`

```c
{
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

