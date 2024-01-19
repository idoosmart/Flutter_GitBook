#### 同步HRV数据


**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                    |
| ---------- | -------- | ------------------------------------------- |
| year       | int      | 数据日期 年                                 |
| month      | int      | 数据日期 月                                 |
| day        | int      | 数据日期 日                                 |
| start_time | int      | 开始时间,单位秒,距离0点的偏移               |
| items      | 集合     | HRV数据详情，`min_offset`&`hrv_value`的集合 |

| 字段名     | 字段类型 | 字段说明          |
| ---------- | -------- | ----------------- |
| min_offset | int      | 默认偏移 单位分钟 |
| hrv_value  | int      | HRV数据           |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "items":[
        {
            "min_offset":5,
            "hrv_value":0
        },
        {
            "min_offset":5,
            "hrv_value":0
        }
    ]
}
```
