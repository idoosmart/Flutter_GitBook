### 设置、查询应用列表样式


功能表:supportOperateListStyle

**Flutter示例：**

```dart
/// 设置、查询应用列表样式
setApplicationListStyle(
    evtBase: _VBusEvtBase.base_app_set,
    evtType: _VBusEvtType.vbus_evt_func_v3_application_list_style)

/// v3 设置应用列表样式
libManager.send(evt: CmdEvtType.setApplicationListStyle, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                                     |
| -------------- | -------- | ------------------------------------------------------------ |
| version        | int      | 协议库版本号                                                 |
| operate        | int      | 操作类型 1:设置 2:查询 3:删除                                                 |
| font_color      | int      | 字体颜色                      |
| name        | string      | 样式名字                                                 |
| wallpaper_version      | int      | 背景壁纸版本                     |

`示例：`

```c
{
  "operate": 1,
  "font_color": 1,
  "name": 1,
  "wallpaper_version": 1
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                  |
| -------- | -------- | ------------------------- |
| version  | int      | 协议库版本号              |
| error_code | int      | 错误码 0成功，非0是错误码 |
| operate        | int      | 操作类型 1:设置 2:查询 3:删除                                            |
| application_list_total_num        | int      | 应用列表壁纸的总数量                                             |
| user_application_list_item_num      | int      | 应用列表壁纸的已安装数量                      |
| application_list_capacity_size      | int      | 应用列表壁纸的总容量，单位Byte                     |
| user_application_list_capacity_size      | int      |    应用列表壁纸的已经使用容量，单位Byte                  |
| p_list_item      | 集合      |    已安装的应用列表壁纸列表，查询有效                  |

| 字段名         | 字段类型 | 字段说明                                                  |
| -------------- | -------- | --------------------------------------------------------- |
| sort_number          | int     | 应用列表壁纸序号 从0开始  |
| font_color      | int     | 字体颜色                                  |
| size   | int      | 当前应用列表壁纸占用空间 单位byte                                             |
| name    | string      | 样式名称                                             |
| wallpaper_version    | int      |背景壁纸版本                                        |


`示例：`

```c
{
  "operate": 1,
  "error_code":0,
  "application_list_total_num": 1,
  "user_application_list_item_num": 1,
  "application_list_capacity_size": 1024,
  "user_application_list_capacity_size": 1024,
  "p_list_item": {
    "sort_number":0,
    "font_color": 6,
    "size": 1024,
    "name": "",
    "wallpaper_version": 0
  }
}
```

