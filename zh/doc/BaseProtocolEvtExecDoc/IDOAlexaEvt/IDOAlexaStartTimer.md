### APP开始定时器功能


功能表:getVoiceTransmission

**App下发的json字段**:

| 字段名             | 字段类型 | 字段说明                                                     |
| ------------------ | -------- | ------------------------------------------------------------ |
| delay_time         | int      | 设置对应的秒表数据                                           |
| index              | int      | 从0开始                                                      |
| operate_timer_flag | int      | 操作标志位  <br />0：增加;<br />1：删除秒表（index确定）<br />255：取消所有的秒表 |

`示例：`

```c
{
    "delay_time":10,
    "index":0,
    "operate_timer_flag":0
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
