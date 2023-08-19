### 设置删除文件


**Flutter示例：**

```dart
/// 删除日志事件号
setClearOperation(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_clear_operations),

/// 删除日志
libManager.send(evt: CmdEvtType.setClearOperation, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                           |
| ------ | -------- | ---------------------------------- |
| type   | int      | 1：过热日志<br />2：电池日志 |

`示例：`

```c
{
  "type":1
}
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明               |
| ------ | -------- | ---------------------- |
| state  | int      | 0成功<br />1失败 |

示例：
```c
{
  "state":0
}
```

