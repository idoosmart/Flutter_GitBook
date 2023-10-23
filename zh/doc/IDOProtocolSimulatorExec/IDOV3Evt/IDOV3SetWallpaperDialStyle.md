### V3设置壁纸表盘颜色和位置


功能表:setWatchPhotoPositionMove

**Flutter示例：**

```dart
/// v3 设置壁纸表盘列表事件号
setWallpaperDialReplyV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_wallpaper_dial_reply),

/// v3 设置壁纸表盘列表
libManager.send(evt: CmdEvtType.setWallpaperDialReplyV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| operate           | int      | 操作  0 ：查询, 1： 设置, 2： 删除壁纸表盘          |
| location          | int      | 设置的位置信息 参考九宫格<br />0：无效<br />1：表盘（上左）<br />2：表盘（上中）<br />3：表盘（上右) <br />4：表盘（中左）<br />5：表盘（中中）<br />6：表盘（中右）<br />7：表盘（下左）<br />8：表盘（下中）<br />9：表盘（下右） |
| hide_type         | int      | 隐藏类型<br />0：全部显示<br />1：隐藏子控件(图标和数字)     |
| time_color        | int      | 时间控件颜色  <br />1个Byte预留 + R(1BYTE) + G(1BYTE) + B (1BYTE) |
| widget_type       | int      | 控件类型<br />1：星期/日期<br />2：步数<br />3：距离<br />4：卡路里<br />5：心率<br />6：电量 |
| widget_icon_color | int      | 小控件图标颜色 1个Byte预留 + R(1BYTE) + G(1BYTE) + B (1BYTE) |
| widget_num_color  | int      | 小控件数字颜色 1个Byte预留 + R(1BYTE) + G(1BYTE) + B (1BYTE) |

`示例：`

```c
{
    "operate":0,
    "location":0,
    "hide_type":0,
    "time_color":0,
    "widget_type":0,
    "widget_icon_color":0,
    "widget_num_color":0
}
```

**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| err_code          | int      | 0成功  非0失败                                               |
| operate           | int      | 操作  <br />0 ：查询<br />1： 设置<br />2： 删除壁纸表盘 |
| location          | int      | 设置的位置信息                                               |
| hide_type         | int      | 隐藏类型                                                     |
| time_color        | int      | 时间控件颜色                                                 |
| widget_type       | int      | 控件类型                                                     |
| widget_icon_color | int      | 小控件图标颜色 1个Byte预留 + R(1BYTE) + G(1BYTE) + B (1BYTE) |
| widget_num_color  | int      | 小控件数字颜色 1个Byte预留 + R(1BYTE) + G(1BYTE) + B (1BYTE) |

`示例：`

```c
{
    "err_code":0,
    "operate":0,
    "location":1,
    "hide_type":1,
    "time_color":16777215,
    "widget_type":1,
    "widget_icon_color":0,
    "widget_num_color":65535
}
```
