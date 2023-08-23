#### 获取GPS和多运动同步的包总数


**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
|        |          |          |

**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明             |
| --------------- | -------- | -------------------- |
| activity_count  | int      | 活动(多运动)数据个数 |
| activity_packet | int      | 活动数据所有包的数量 |
| gps_count       | int      | GPS数据个数          |
| gps_packet      | int      | GPS数据所有包的数量  |

`示例：`

```c
{
    "activity_count":2,
    "activity_packet":1,
    "gps_count":2,
    "gps_packet":1
}
```
