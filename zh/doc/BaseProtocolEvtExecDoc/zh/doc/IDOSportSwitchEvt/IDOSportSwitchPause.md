#### APP发送交换运动数据暂停


**App下发的json字段**:

| 字段名       | 字段类型 | 字段说明    |
| ------------ | -------- | ----------- |
| day          | int      | 开始时间 日 |
| hour         | int      | 开始时间 时 |
| minute       | int      | 开始时间 分 |
| second       | int      | 开始时间 秒 |
| sport_hour   | int      |             |
| sport_minute | int      |             |
| sport_second | int      |             |

`示例：`

```c
{
    "day":26,
    "hour":10,
    "minute":54,
    "second":50,
    "sport_hour":10,
    "sport_minute":54,
    "sport_second":50
}
```
**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                |
| -------- | -------- | ------------------------------------------------------- |
| err_code | int      | err_code<br/>0：成功<br />1：没有进入运动模式失败 |

`示例：`

```c
{
    "err_code":0
}
```

