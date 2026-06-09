#### 同步GPS


**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明    |
| ------------- | -------- | ----------- |
| year          | int      | 数据日期 年 |
| month         | int      | 数据日期 月 |
| day           | int      | 数据日期 日 |
| hour          | int      | 数据日期 时 |
| minute        | int      | 数据日期 分 |
| second        | int      | 数据日期 秒 |
| data_interval | int      | 数据偏移    |
| time_zone         | int      | 时区扩大 100 倍返回，如时区 8 对应 800，5.5 对应 550<br />仅当 `supportSyncHealthDataWithTimeZone` 功能表开启时有效 |
| string_items   | char [] | GPS数组详情 |

`示例：`

```c
{

}
```

