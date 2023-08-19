### V3获取表盘列表(新接口)


功能表:getNewWatchList

**Flutter示例：**

```dart
/// v3 获取表盘列表事件号
getWatchListV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_watch_list_new),

/// v3 获取表盘列表
libManager.send(evt: CmdEvtType.getWatchListV3, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名                   | 字段类型 | 字段说明                                                     |
| ------------------------ | -------- | ------------------------------------------------------------ |
| local_watch_num          | int      | 本地表盘的总个数                                             |
| cloud_watch_num          | int      | 云端表盘的总个数                                             |
| wallpaper_watch_num      | int      | 壁纸表盘的总个数                                             |
| user_cloud_watch_num     | int      | 云端表盘的已经使用个数                                       |
| user_wallpaper_watch_num | int      | 壁纸表盘的已经使用个数                                       |
| now_show_watch_name      | char []   | 当前显示的表盘ID 最大30个字节                                |
| watch_frame_main_version | int      | 框架版本号 从1开始                                           |
| file_max_size            | int      | 单个文件最大size  单位KB                                     |
| list_item_numb           | int      | 表盘列表详情个数                                             |
| watch_capacity_size | int | 表盘的总容量<br />固件开启V3_support_watch_capacity_size_display有效,否则字段赋0 |
| user_watch_capacity_size | int | 表盘的已经使用容量<br />固件开启V3_support_watch_capacity_size_display有效,否则字段赋0 |
| usable_max_download_space_size | int | 最大的可用表盘下载连续空间大小<br />固件开启V3_support_watch_capacity_size_display有效,否则字段赋0 |
| item                     | 集合     | 表盘列表详情 <br />type & watch_version & sort_number &name &size的集合 |

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| type          | int      | 表盘类型   <br />1：普通表盘  2：壁纸表盘  3：云表盘         |
| watch_version | int      | 当前的表盘版本号 云表盘起作用                                |
| sort_number   | int      | 表盘序号                                                     |
| name          | char []  | 表盘名称                                                     |
| size          | int      | 当前表盘占用空间 单位byte<br />固件开启v3_support_get_watch_size功能表有效, 否则字段无效 |

`示例：`

```c
{
    "local_watch_num":0,
    "cloud_watch_num":0,
    "wallpaper_watch_num":0,
    "user_cloud_watch_num":0,
    "user_wallpaper_watch_num":0,
    "now_show_watch_name":"w123.iwf",
    "watch_frame_main_version":0,
    "file_max_size":0,
    "list_item_numb":2,
    "watch_capacity_size":0,
    "user_watch_capacity_size":0,
    "usable_max_download_space_size":0,
    "item":[
        {
            "type":0,
            "watch_version":0,
            "sort_number":0,
            "name":"w123.iwf",
            "size":0
        },
        {
            "type":0,
            "watch_version":0,
            "sort_number":0,
            "name":"w846.iwf",
            "size":0
        }
    ]
}
```
