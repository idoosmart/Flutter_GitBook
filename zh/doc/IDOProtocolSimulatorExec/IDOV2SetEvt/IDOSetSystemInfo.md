### 设置手机操作系统


功能表：getSupportAppSendPhoneSystemInfo

**Flutter示例：**

```dart
/// 设置app系统事件号
setAppOS(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_app_os),

/// 设置app系统
libManager.send(evt: CmdEvtType.setAppOS, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名         | 字段类型 | 字段说明                                     |
| -------------- | -------- | -------------------------------------------- |
| system         | int      | 手机操作系统 <br />0x1:ios <br />0x2:android |
| system_version | int      | 手机系统版本号 <br />预留                    |

`示例：`

```c
{
  "system" : 1
}
```

