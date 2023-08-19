### V3设置表盘顺序


功能表:setWatchDialSort

**Flutter示例：**

```dart
/// 设置表盘顺序事件号
setWatchDialSort(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_set_watch_dial_sort),

/// 设置表盘顺序
libManager.send(evt: CmdEvtType.setWatchDialSort, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名         | 字段类型 | 字段说明                                              |
| -------------- | -------- | ----------------------------------------------------- |
| sort_item_numb | int      | 表盘排序列表内容个数                                  |
| p_sort_item    | 集合     | 表盘排序列表内容<br />type & sort_number & name的集合 |

| 字段名      | 字段类型 | 字段说明                                              |
| ----------- | -------- | ----------------------------------------------------- |
| type        | int      | 表盘类型  <br /> 1：普通表盘  2：壁纸表盘   3：云表盘 |
| sort_number | int      | 序号，从0开始，不超过设备支持的表盘总个数             |
| name        | char []  | 表盘id  最大值30个字节                                |

`示例：`

```c
{
  "sort_item_numb": 2,
  "p_sort_item":[
      {
          "type":1,
            "sort_number":0,
            "name":"w123.iwf"
      },
      {
            "type":1,
            "sort_number":1,
            "name":"w555.iwf"
        }
  ]
}
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明              |
| -------- | -------- | --------------------- |
| version  | int      | 协议版本号            |
| err_code | int      | 错误码 0成功，非0失败 |

`示例：`

```c
{
  "version": 0,
  "err_code":0
}
```
