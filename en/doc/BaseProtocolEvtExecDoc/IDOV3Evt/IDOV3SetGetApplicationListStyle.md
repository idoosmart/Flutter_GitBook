### Setting and Querying the Application List Style

Function Table: supportOperateListStyle

**Flutter Example:**

```dart
/// Setting and Querying the Application List Style
setApplicationListStyle(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_func_v3_application_list_style)

/// Set the v3 application list style
libManager.send(evt: CmdEvtType.setApplicationListStyle, json: jsonEncode(json));
```

**JSON Fields Sent by the App**:

| Field Name | Field Type | Field Description |
| -------------- | -------- | ------------------------------------------------------------ |
| version | int | Protocol Library Version Number |
| operate | int | Operation Type 1: Set 2: Query 3: Delete |
| font_color | int | Font color |
| name | string | Style name |
| wallpaper_version | int | Background wallpaper version |

`Example:`

```c
{
"operate": 1,
"font_color": 1,
"name": 1,
"wallpaper_version": 0
}
```

**JSON fields received by the app**:

| Field name | Field type | Field description |
| -------- | -------- | ------------------------- |
| version | int | Protocol library version number |
| error_code | int | Error code: 0 for success, non-zero for error code |
| operate | int | Operation type: 1: Set 2: Query 3: Delete |
| application_list_total_num | int | Total number of wallpapers in the application list |
| user_application_list_item_num | int | Number of installed wallpapers in the application list |
| application_list_capacity_size | int | Total capacity of application list wallpapers, in bytes |
| user_application_list_capacity_size | int | Used capacity of application list wallpapers, in bytes |
| p_list_item | Collection | List of installed application list wallpapers, valid for query |

| Field name | Field type | Field description |
| -------------- | -------- | --------------------------------------------------------- |
| sort_number | int | Application list wallpaper sequence, starting from 0 |
| font_color | int | Font color |
| size | int | Space occupied by the current application list wallpaper, in bytes |
| name | string | Style name |
| wallpaper_version | int | Background wallpaper version |

`Example:`

```c
{
"operate": 1,
"error_code": 0,
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