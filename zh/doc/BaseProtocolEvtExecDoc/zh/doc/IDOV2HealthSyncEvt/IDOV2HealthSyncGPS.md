#### 同步GPS数据


**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
|        |          |          |

**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明      |
| ------------- | -------- | ------------- |
| year          | int      | 年            |
| month         | int      | 月            |
| day           | int      | 日            |
| hour          | int      | 时            |
| minute        | int      | 分            |
| second        | int      | 秒            |
| data_interval | int      | 数据间隔 单位秒      |
| items         | char []   | gps坐标字符串 |

`示例：`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "hour":10,
    "minute":22,
    "second":36,
    "data_interval":5,
    "items":"",
}
```

