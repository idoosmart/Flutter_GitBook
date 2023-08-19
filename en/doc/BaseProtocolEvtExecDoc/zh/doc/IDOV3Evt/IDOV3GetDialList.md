### V3获取表盘列表


功能表:getNewWatchList

**Flutter示例：**

```dart
/// 获取表盘列表事件号
getWatchFaceList(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_get_watch_face_list),

/// 获取表盘列表
libManager.send(evt: CmdEvtType.getWatchFaceList, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名          | 字段类型 | 字段说明                     |
| --------------- | -------- | ---------------------------- |
| version         | int      | 协议版本号                   |
| available_count | int      | 剩余个数，可用文件个数       |
| file_max_size   | int      | 单个文件最大size 单位KB      |
| item            | 集合     | 表盘列表详情，file_name的集合 |

| 字段名    | 字段类型 | 字段说明 |
| --------- | -------- | -------- |
| file_name | char []  | 表盘名称 |

`示例：`

```c
{
    "version":0,
    "available_count":0,
    "file_max_size":140,
    "item":[
        {
            "file_name":"w256.iwf"
        },
        {
            "file_name":"w174.iwf"
        }
    ]
}
```
