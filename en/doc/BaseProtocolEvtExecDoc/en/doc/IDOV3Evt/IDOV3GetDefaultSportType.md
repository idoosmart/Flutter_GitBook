### V3 Gets the default type of motion


**JSON received by the app**:

| Field Name       | Field Type | Field Description                                           |
| ---------------- | ---------- | ------------------------------------------------------------ |
| default_show_num | int        | Number of currently displayed items                         |
| min_show_num     | int        | Minimum supported number of items                           |
| max_show_num     | int        | Maximum supported number of items                           |
| is_supports_sort | int        | Whether default sorting is supported or not, 0x0 for not supported, 0x01 for supported |
| sport_type       | int []     | Array of sport types<br />Valid only when is_supports_sort=1<br />The array length is default_show_num with zero-padding for empty positions |

`Example:`

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