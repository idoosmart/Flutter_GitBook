### 控制清除手环缓存


**Flutter示例：**

```dart
/// 清除手环缓存事件号
clearCache(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_clear_cache),

/// 清除手环缓存
libManager.send(evt: CmdEvtType.clearCache, json: jsonEncode(json));
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

