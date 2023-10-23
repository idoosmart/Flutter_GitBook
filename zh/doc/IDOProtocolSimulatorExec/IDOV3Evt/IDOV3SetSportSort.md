### V3设置运动类型排序


功能表:getSportsTypeV3

**Flutter示例：**

```dart
/// 设置运动类型排序事件号
setSportSortV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_sport_sort),

/// 设置运动类型排序
libManager.send(evt: CmdEvtType.setSportSortV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                               |
| ------ | -------- | -------------------------------------- |
| num    | int      | 运动类型详情个数，最大30个             |
| item   | 集合     | 运动类型排序详情，`index`&`type`的集合 |

| 字段名 | 字段类型 | 字段说明                       |
| ------ | -------- | ------------------------------ |
| index  | int      | 排序序号，0无效，从1开始       |
| type   | int      | 运动类型，具体看定义的运动类型 |

`示例：`

```c
{
    "num":3,
    "item":[
        {
            "index":1,
            "type":2,
        },
        {
            "index":2,
            "type":22,
        },
        {
            "index":3,
            "type":33,
        }
    ]
}
```
