### V3获取屏幕信息


**Flutter示例：**

```dart
/// 获取屏幕信息事件号
getWatchDialInfo(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_get_screen_ifno),

/// 获取屏幕信息
libManager.send(evt: CmdEvtType.getWatchDialInfo, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明              |
| ----------- | -------- | --------------------- |
| width       | int      | 屏幕宽度              |
| height      | int      | 屏幕高度              |
| format      | int      | 颜色格式              |
| sizex100    | int      | 尺寸 x100             |
| family_name | char []   | 家族名称 最大10个字节 |
| block_size  | int      | 压缩块大小            |

`示例：`

```c
{
  "block_size" : 4096,
  "family_name" : "139",
  "format" : 133,
  "height" : 280,
  "sizex100" : 0,
  "width" : 240
}
```
