### V3设置查询运动子项数据排列


功能表:setSet20SportParamSort

**Flutter示例：**

```dart
/// v3 设置运动子项数据排列事件号
setBaseSportParamSortV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_base_sport_param_sort),

/// v3 设置运动子项数据排列
libManager.send(evt: CmdEvtType.setBaseSportParamSortV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                            |
| ----------------- | -------- | ----------------------------------- |
| version           | int      | 协议库版本号                        |
| operate           | int      | 操作 <br />0：无效  1：查询 2：设置 |
| sport_type        | int      | 运动类型                            |
| now_user_location | int      | 当前的显示已经添加的运动位置        |
| all_num           | int      | 运动排序列表中的个数                |
| items             | int []    | 设置列表 最大值50个字节             |

`示例：`

```c
{
    "version":0,
    "operate":2,
    "sport_type":2,
    "now_user_location":2,
    "all_num":5,
    "items":[
        1,
        2,
        3,
        4,
        5
    ]
}
```

**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| version           | int      | 协议库版本号                                                 |
| err_code          | int      | 0成功  非0失败                                               |
| operate           | int      | 操作 <br />0：无效  1：查询 2：设置                          |
| sport_type        | int      | 运动类型                                                     |
| now_user_location | int      | 当前的显示已经添加的运动位置，app根据这个位置显示，前面的对应的设备是添加的，这边位置后面是未添加的，查询起作用 |
| all_num           | int      | 运动排序列表详情个数 查询起作用                              |
| items             | int []   | 运动排序查询的列表 运动子项排序枚举列表                      |

`示例：`

```c
{
    "version":0,
    "err_code":0,
    "operate":0,
    "sport_type":0,
    "now_user_location":0,
    "all_num":0,
    "items":[]
}
```
