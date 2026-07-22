### 获取功能表


功能表:每个设备支持

**Flutter示例：**

```dart
/// 获取功能表事件号
getFuncTable(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_func_table_user),

/// 获取功能表
libManager.send(evt: CmdEvtType.getFuncTable, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| ..     |          |          |
