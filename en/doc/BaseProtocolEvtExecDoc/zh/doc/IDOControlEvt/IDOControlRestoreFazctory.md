### 控制设备恢复出厂


**Flutter示例：**

```dart
/// 恢复出厂设置事件号
factoryReset(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_restore_fazctory),

/// 恢复出厂设置
libManager.send(evt: CmdEvtType.factoryReset, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明              |
| ---------- | -------- | --------------------- |
| is_success | int      | 1：成功 <br />0：失败 |

`示例：`

```c
{
    "is_success":0
}
```

