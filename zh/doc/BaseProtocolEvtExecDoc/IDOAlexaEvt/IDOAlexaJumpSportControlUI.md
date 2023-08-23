### ALEXA跳转运动界面


功能表:alexaSetJumpSportUiV3

**App下发的json字段**:

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| sports_type   | int      | 20种运动                                                     |
| v2_sport_type | int      | 100种运动<br />这个字段支持的时候，sports_type赋值0<br />需要固件开启功能表V3_set_100_sport_sort |

`示例：`

```c
{
    "sports_type":0,
    "v2_sport_type":20
}
```

**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明         |
| ---------- | -------- | ---------------- |
| is_success | int      | 1：成功 ， 0失败 |

`示例：`

```c
{
    "is_success":1
}
```
