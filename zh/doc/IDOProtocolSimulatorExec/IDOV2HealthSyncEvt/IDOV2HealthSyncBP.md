#### 同步血压数据


**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                            |
| ------------- | -------- | --------------------------------------------------- |
| year          | int      | 数据日期 年                                         |
| month         | int      | 数据日期 月                                         |
| day           | int      | 数据日期 日                                         |
| sleep_avg_bp  | int      | 睡眠平均血压                          |
| max_bp        | int      | 血压最大值                                          |
| minute_offset | int      | 数据的距离0点的开始时间，单位分钟                   |
| items         | 集合     | 血压详情<br />offset & dias_blood & sys_blood的集合 |

| 字段名     | 字段类型 | 字段说明                                 |
| ---------- | -------- | ---------------------------------------- |
| offset     | int      | 数据的偏移，单位分钟，用于定位数据的时间 |
| dias_blood | int      | 舒张压(低压)                             |
| sys_blood  | int      | 收缩压(高压)                             |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "sleep_avg_bp":86,
    "max_bp":90,
    "minute_offset":15,
    "items":[
        {
            "offset":5,
            "dias_blood":70,
            "sys_blood":90
        },
        {
            "offset":5,
            "dias_blood":69,
            "sys_blood":87
        },
        {
            "offset":5,
            "dias_blood":76,
            "sys_blood":88
        }
    ]
}
```
