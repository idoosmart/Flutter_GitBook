### 设置快捷方式


**Flutter示例：**

```dart
/// 设置快捷方式
setShortcut(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_shortcut),

/// 设置快捷方式
libManager.send(evt: CmdEvtType.setShortcut, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| mode   | int      | 快捷键1的功能<br />0：无效<br />1：快速进入拍照控制<br />2：快速进入运动模式<br />3：快速进入勿扰开关 |

`示例：`

```c
{
  "mode":2
}
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明           |
| -------- | -------- | ------------------ |
| ret_code | int      | 0 成功，非0失败 |

`示例：`

```c
{
  "ret_code":0
}
```
