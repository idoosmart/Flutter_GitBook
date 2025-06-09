#### 同步情绪健康


**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                                 |
| ---------- | -------- | -------------------------------------------------------- |
| year       | int      | 数据日期 年                                              |
| month      | int      | 数据日期 月                                              |
| day        | int      | 数据日期 日                                              |
| start_time | int      | 开始时间,单位分钟,距离0点的偏移                    |
| emotion_health_item_num  | int      | 情绪健康值个数，最大值1440                                                     |
| items      | 集合     | 情绪健康值，`time_offset`&`emotion_health_val`的集合 |

| 字段名     | 字段类型 | 字段说明                                                     |
| ---------- | -------- | ------------------------------------------------------------ |
| time_offset     | int      | 时间偏移，单位分钟                                             |
| emotion_health_val       | int      | 情绪健康值<br/> 0：愉悦<br/>1：平静<br/>2：一般<br/>3：焦虑<br/>4：无效|

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "emotion_health_item_num":0,
    "items":[
        {
            "time_offset":5,
            "emotion_health_val":0
        }
    ]
}
```