### 设置热启动参数


**Flutter示例：**

```dart
/// 设置热启动参数事件号
setHotStartParam(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_hot_start_param),

/// 设置热启动参数
libManager.send(evt: CmdEvtType.setHotStartParam, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名      | 字段类型 | 字段说明   |
| ----------- | -------- | ---------- |
| longitude   | int      | 晶振偏移   |
| latitude    | int      | 经度 x10^6 |
| altitude    | int      | 纬度 x10^6 |
| tcxo_offset | int      | 高度 x10   |

`示例：`


```c
{
    "longitude":2,
    "latitude":0,
    "altitude":0,
    "tcxo_offset":0
}
```
