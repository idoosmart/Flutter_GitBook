### 设置显示模式


功能表: displayMode(SDK待补充)

**Flutter示例：**

```dart
/// 设置显示模式事件号
setDisplayMode(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_display_mode),

/// 设置显示模式
libManager.send(evt: CmdEvtType.setDisplayMode, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| mode   | int      | 模式<br />0：默认，1：横屏， 2:竖屏， 3：（翻转180度） |

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

