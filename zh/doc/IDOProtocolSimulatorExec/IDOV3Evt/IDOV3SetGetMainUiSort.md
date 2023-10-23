### V3设置查询主界面控件排序


功能表:setSetMainUiSort

**Flutter示例：**

```dart
/// v3 设置主界面控件排序事件号
setMainUISortV3(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_main_ui_sort),

/// v3 设置主界面控件排序
libManager.send(evt: CmdEvtType.setMainUISortV3, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名       | 字段类型 | 字段说明                                                     |
| ------------ | -------- | ------------------------------------------------------------ |
| version      | int      | 协议库版本号                                                 |
| operate      | int      | 操作 <br />0：无效  <br />1：查询 <br />2：设置              |
| all_num      | int      | 控件排序列表详情的个数                                       |
| items        | int []    | 控件排序列表详情                                             |
| location_x   | int      | 横轴x 从1开始                                                |
| location_y   | int      | 纵轴y 从1开始 <br /> 一个y就是一个横向的格子                 |
| size_type    | int      | 0：无效  <br />1：大图标  <br />2：小图标                    |
| widgets_type | int      | 控件类型<br />0：无效<br />1：星期/日期<br />2：步数<br />3：距离<br />4：卡路里<br />5：心率<br />6：电量 |

`示例：`

```c
{
    "version":0,
    "operate":2,
    "all_num":3,
    "items":[
        1,
        2,
        3
    ],
    "location_x":1,
    "location_y":1,
    "size_type":2,
    "widgets_type":1
}
```

**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| version       | int      | 协议库版本号                                                 |
| err_code      | int      | 0成功  非0失败                                               |
| operate       | int      | 操作 <br />0：无效  <br />1：查询 <br />2：设置              |
| all_num       | int      | 固件当前的显示的列表的个数                                   |
| items         | 集合     | 固件当前的显示的列表排列的情况 <br />`location_x` & `location_y` & `size_type` & `support_size_type` & `widgets_type`的集合 |
| support_items | 集合     | 固件支持的所有的组件类型  <br />`support_size_type` & `widgets_type`的集合 |

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| location_x        | int      | 横轴x 从1开始                                                |
| location_y        | int      | 纵轴y 从1开始  <br />一个y就是一个横向的格子                 |
| size_type         | int      | 0：无效<br />1：大图标<br />2：小图标                        |
| support_size_type | int      | 固件支持可以编辑的图标类型<br />0：无效<br />1：大图标<br />2：小图标<br />3：大图标+小图标 |
| widgets_type      | int      | 控件类型<br />0：无效<br />1：星期/日期<br />2：步数<br />3：距离<br />4：卡路里<br />5：心率<br />6：电量 |

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| support_size_type | int      | 固件支持可以编辑的图标类型<br />0： 无效<br />1：大图标<br />2：小图标<br />3：大图标+小图标 |
| widgets_type      | int      | 控件类型<br />0：无效<br />1：星期/日期<br />2：步数<br />3：距离<br />4：卡路里<br />5：心率<br />6：电量 |

`示例：`

```c
{
    "version":0,
    "err_code":0,
    "operate":0,
    "all_num":0,
    "items":[],
    "location_x":0,
    "location_y":0,
    "size_type":0,
    "widgets_type":0
}
```
