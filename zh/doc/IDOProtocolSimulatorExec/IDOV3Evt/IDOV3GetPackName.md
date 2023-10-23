### V3获取包名


功能表:getNotifyIconAdaptive

**Flutter示例：**

```dart
/// 获取应用包名事件号
getPackName(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.tran_json_get_app_pack_name
),

/// 获取应用包名
libManager.send(evt: CmdEvtType.getPackName, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名      | 字段类型 | 字段说明                                                     |
| ----------- | -------- | ------------------------------------------------------------ |
| operat_flag | int      | 0：获取全部的<br />1：获取增量数据                           |
| last_id     | int      | operat_flag等于获取增量数据 起作用<br />获取增量数据的时候需要传上次返回的ID，继续获取 |

`示例：`

```c
{
    "operat_flag":0,
    "last_id":0
}
```

**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| version       | int      | 协议库版本号                                                 |
| icon_width    | int      | 宽度(像素块大小)                                             |
| icon_height   | int      | 高度(像素块大小)                                             |
| format        | int      | 颜色格式                                                     |
| block_size    | int      | 压缩块大小                                                   |
| pack_name_num | int      | 包名的个数                                                   |
| package_num   | int      | 包名信息详情总个数                                           |
| items         | 集合     | app包名信息详情<br />item_id & evt_type & need_sync_icon & msg_cout & pack_name_len & pack_name_array的集合 |

| 字段名          | 字段类型 | 字段说明                                                     |
| --------------- | -------- | ------------------------------------------------------------ |
| item_id         | int      | 每个包名给一个id，累加，后续用来拿增量数据，由0开始          |
| evt_type        | int      | 事件类型                                                     |
| need_sync_icon  | int      | 需要更新图标数据 <br />0：不需要更新 <br />1：需要更新icon<br />2：需要更新app名<br />3：icon和app都需要更新 |
| msg_cout        | int      | 该条消息收到次数                                             |
| pack_name_len   | int      | 包名长度 最大50个字节                                        |
| pack_name_array | char []  | 包名                                                         |

`示例：`

```json
{
    "version":0,
    "icon_width":200,
    "icon_height":120,
    "format":133,
    "block_size":1024,
    "pack_name_num":0,
    "package_num":0,
    "items":null
}
```

