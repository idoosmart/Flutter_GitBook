### 设置控制拍照


功能表：bleControlTakePhoto(SDK待补充)

**Flutter示例：**

```dart
/// 控制拍照事件号
setTakePicture(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_take_picture),

/// 控制拍照
libManager.send(evt: CmdEvtType.setTakePicture, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明             |
| ------ | -------- | -------------------- |
| on_off | int      | 0 关<br />1 开 |

`示例：`

```c
{
  "on_off": 0
}
```

