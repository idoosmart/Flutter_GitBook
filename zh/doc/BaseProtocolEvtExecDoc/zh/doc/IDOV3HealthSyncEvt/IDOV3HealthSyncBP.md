#### 同步血压数据


**App收到的json字段**：

| 字段名       | 字段类型 | 字段说明                                    |
| ------------ | -------- | ------------------------------------------- |
| year         | int      | 数据日期 年                                 |
| month        | int      | 数据日期 月                                 |
| day          | int      | 数据日期 日                                 |
| start_time   | int      | 开始时间,单位秒,距离0点的偏移               |
| sleep_avg_bp | int      | 睡眠平均血压值                              |
| max_bp       | int      | 血压最大值                                  |
| item_count   | int      | 血压详情个数                                |
| items        | 集合     | 血压详情，offset&sys_blood&dias_blood的集合 |

| 字段名     | 字段类型 | 字段说明                                        |
| ---------- | -------- | ----------------------------------------------- |
| offset     | int      | 数据偏移 单位：分钟  （血压数据间隔按分钟偏移） |
| sys_blood  | int      | 较大收缩压                                      |
| dias_blood | int      | 较小收缩压                                      |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "sleep_avg_bp":0,
    "max_bp":0,
    "item_count":3,
    "items":[
        {
            "offset":5,
            "sys_blood":120,
            "dias_blood":70
        },
        {
            "offset":5,
            "sys_blood":120,
            "dias_blood":70
        },
        {
            "offset":5,
            "sys_blood":120,
            "dias_blood":70
        }
    ]
}
```