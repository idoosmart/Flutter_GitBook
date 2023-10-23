### V3获取运动默认的类型


**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                                     |
| ---------------- | -------- | ------------------------------------------------------------ |
| default_show_num | int      | 显示当前的数量                                               |
| min_show_num     | int      | 最小支持的数量                                               |
| max_show_num     | int      | 最大支持的数量                                               |
| is_supports_sort | int      | 是否支持默认排序,0x0 不支持,0x01 支持                        |
| sport_type       | int []   | 运行类型<br />is_supports_sort=1时有效<br />数量为default_show_num,空位填0 |

`示例：`

```c
{
    "default_show_num":4,
    "min_show_num":1,
    "max_show_num":4,
    "is_supports_sort":1,
    "sport_type":[
        1,
        2,
        3,
        4
    ]
}
```

