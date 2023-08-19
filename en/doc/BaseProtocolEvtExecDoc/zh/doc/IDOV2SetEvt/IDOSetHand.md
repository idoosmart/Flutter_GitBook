### 设置左右手


功能表: ////TODO (未找到对应功能表)

**Flutter示例：**

```dart
/// 设置左右手事件号
setHand(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_hand),

/// 设置左右手
libManager.send(evt: CmdEvtType.setHand, json: jsonEncode(json));
```

**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                    |
| ------ | -------- | --------------------------- |
| hand   | int      | 0：左手 <br />1：右手 |

`示例：`

```c
{
  "hand":0
}
```

