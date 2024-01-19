### V3设置查询100种运动排序


功能表:getSportsTypeV3

**Flutter示例：**

```dart
/// v3 新的100种运动排序事件号
set100SportSortV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_100_sport_sort),

/// v3 新的100种运动排序
libManager.send(evt: CmdEvtType.set100SportSortV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                            |
| ----------------- | -------- | ----------------------------------- |
| version           | int      | 协议库版本号                        |
| operate           | int      | 操作 <br />0：无效  <br />1：查询 <br />2：设置 |
| now_user_location | int      | 当前的显示已经添加的运动位置        |
| all_num           | int      | 运动排序列表中的个数                |
| items_set         | int []    | 运动排序列表 最大值150个        |

`示例：`

```c
{
    "version":0,
    "operate":2,
    "now_user_location":2,
    "all_num":6,
    "items_set":[
        2,
        3,
        50,
        198,
        20,
        32
    ]
}
```

**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| version           | int      | 协议库版本号                                                 |
| err_code          | int      | 0成功  非0失败                                               |
| operate           | int      | 操作 <br />0：无效  <br />1：查询<br />2：设置               |
| min_show_num      | int      | 最少显示个数  最少是1个                                      |
| max_show_num      | int      | 最大显示个数  最大是20个                                     |
| now_user_location | int      | 当前的显示已经添加的运动位置，app根据这个位置显示，前面的对应的设备是添加的，这边位置后面是未添加的，查询起作用 |
| all_num           | int      | 运动排序列表详情个数 <br />查询起作用<br />最多150组items    |
| items             | 集合     | 运动排序查询的列表 <br />`type` & `flag`的集合<br />查询起作用 |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| type   | int      | 运动类型                                                     |
| flag   | int      | 00都没有下载<br />bit0：小图标已下载  <br />bit1：大图标已下载  <br />bit2：中等图标已下载  <br />bit3：最小图标已下载 |

`示例：`

```c
{
    "version":0,
    "err_code":0,
    "operate":2,
    "min_show_num":1,
    "max_show_num":20,
    "now_user_location":2,
    "all_num":6,
    "items":null
}
```