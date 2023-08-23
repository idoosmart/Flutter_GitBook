### V3语音设置提醒


功能表:getVoiceTransmission

**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| item   | 集合     | reminder_id & status & year & month & day & hour & minute & reminder_string的集合 |

| 字段名          | 字段类型 | 字段说明                                             |
| --------------- | -------- | ---------------------------------------------------- |
| reminder_id     | int      | id<br />从1到5                                       |
| status          | int      | 开关状态<br />170关闭，85 打开                       |
| year            | int      | 年                                                   |
| month           | int      | 月                                                   |
| day             | int      | 日                                                   |
| hour            | int      | 时                                                   |
| minute          | Int      | 分                                                   |
| sec             | int      | 秒<br />需要功能表支持key：V3_alexa_reminder_add_sec |
| reminder_string | char []  | 提醒内容<br />最大值128个字节                        |

`示例：`

```c
{
    "item":[
        {
            "reminder_id":1,
            "status":85,
            "year":2022,
            "month":12,
            "day":26,
            "hour":12,
            "minute":30,
            "sec":30,
            "reminder_string":"记得吃饭"
        },
        {
            "reminder_id":2,
            "status":85,
            "year":2022,
            "month":12,
            "day":26,
            "hour":23,
            "minute":30,
            "sec":30,
            "reminder_string":"记得睡觉"
        },
        {
            "reminder_id":3,
            "status":85,
            "year":2022,
            "month":12,
            "day":26,
            "hour":20,
            "minute":00,
            "sec":30,
            "reminder_string":"记得洗澡"
        },
        {
            "reminder_id":4,
            "status":85,
            "year":2022,
            "month":12,
            "day":27,
            "hour":8,
            "minute":0,
            "sec":30,
            "reminder_string":"记得起床"
        },
        {
            "reminder_id":5,
            "status":170,
            "year":2022,
            "month":12,
            "day":27,
            "hour":14,
            "minute":0,
            "sec":30,
            "reminder_string":""
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

