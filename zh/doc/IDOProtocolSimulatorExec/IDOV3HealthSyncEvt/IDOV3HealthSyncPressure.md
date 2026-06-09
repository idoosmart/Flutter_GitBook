#### 同步压力


**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                         |
| ---------- | -------- | ------------------------------------------------ |
| year       | int      | 数据日期 年                                      |
| month      | int      | 数据日期 月                                      |
| day        | int      | 数据日期 日                                      |
| start_time | int      | 开始时间,单位秒,距离0点的偏移                    |
| data_type  | int      | ~~0为无效,1为一个值,2为最大和最小值~~ (预留字节) |
| time_zone         | int      | 时区扩大 100 倍返回，如时区 8 对应 800，5.5 对应 550<br />仅当 `supportSyncHealthDataWithTimeZone` 功能表开启时有效 |
| items      | 集合     | `offset` & `value`的集合                         |

| 字段名 | 字段类型 | 字段说明      |
| ------ | -------- | ------------- |
| offset | int      | 偏移 单位分钟 |
| value  | int      | 压力值        |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "data_type":1,
    "items":[
        {
            "offset":30,
            "value":30,
        },
        {
            "offset":30,
            "value":30,
        }
    ]
}
```
