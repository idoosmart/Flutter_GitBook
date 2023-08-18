#### 设备通知APP交换数据结束


**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明               |
| ------------- | -------- | ---------------------- |
| day           | int      | 开始时间 日            |
| hour          | int      | 开始时间 时            |
| minute        | int      | 开始时间 分            |
| second        | int      | 开始时间 秒            |
| duration      | int      | 持续时长 单位s         |
| calories      | int      | 卡路里 单位大卡        |
| distance      | int      | 距离 单位0.01km        |
| sport_type    | int      | 运动类型               |
| avg_hr_value  | int      | 平均心率               |
| max_hr_value  | int      | 最大心率               |
| burn_fat_mins | int      | 脂肪燃烧时长 单位分钟  |
| aerobic_mins  | int      | 心肺锻炼时长 单位分钟  |
| limit_mins    | int      | 极限锻炼时长 单位分钟  |
| is_save       | int      | 0:不保存，1:保存 |

`示例：`

```c
{
    "day":26,
    "hour":10,
    "minute":50,
    "second":50,
    "duration":10,
    "calories":10,
    "distance":10,
    "sport_type":1,
    "avg_hr_value":80,
    "max_hr_value":90,
    "burn_fat_mins":0,
    "aerobic_mins":0,
    "limit_mins":0,
    "is_save":0
}
```

**App下发的json字段**:

| 字段名   | 字段类型 | 字段说明        |
| -------- | -------- | --------------- |
| err_code | int      | err_code<br/>0：成功<br />1：没有进入运动模式失败     |
| duration | int      | 持续时长 单位s  |
| calories | int      | 卡路里 单位大卡 |
| distance | int      | 距离 单位0.01km |

`示例：`

```c
{
    "err_code":0,
    "duration":10,
    "calories":50,
    "distance":50
}
```

