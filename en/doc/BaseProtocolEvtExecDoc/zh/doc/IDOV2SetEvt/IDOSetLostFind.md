### 设置防丢模式


功能表: antilost(SDK待补充)

**Flutter示例：**

```dart
/// 设置防丢事件号
setLostFind(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_lost_find),

/// 设置防丢
libManager.send(evt: CmdEvtType.setLostFind, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| mode   | int      | 方式<br />0：不防丢，1：近距离防丢，2:中距离防丢，3：远距离防丢 |

`示例：`

```c
{
  "mode":0
}
```



**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明         |
| ----------- | -------- | ---------------- |
| status_code | int      | 0：成功，非0失败 |

`示例：`

```c
{
  "status_code":0
}
```

