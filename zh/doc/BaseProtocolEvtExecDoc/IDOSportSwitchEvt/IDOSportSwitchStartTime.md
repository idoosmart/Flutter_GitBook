#### APP发送交换运动数据开始时间


**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明    |
| ------ | -------- | ----------- |
| day    | int      | 开始时间 日 |
| hour   | int      | 开始时间 时 |
| minute | int      | 开始时间 分 |
| second | int      | 开始时间 秒 |

`示例：`

```c
{
    "day":26,
    "hour":10,
    "minute":55,
    "second":53
}
```
**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明    |
| ----------- | -------- | ----------- |
| hour        | int      | 运动时间 时 |
| minute      | int      | 运动时间 分 |
| second      | int      | 运动时间 秒 |
| millisecond | int      | 待定        |

`示例：`

```c
{
    "day":26,
    "hour":10,
    "minute":56,
    "millisecond":0
}
```

