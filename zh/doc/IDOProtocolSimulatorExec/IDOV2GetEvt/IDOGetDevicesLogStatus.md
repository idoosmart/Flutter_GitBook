### 获取设备的日志状态


功能表:getDeviceLogState

**Flutter示例：**

```dart
/// 获取设备的日志状态事件号
getDeviceLogState(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_devices_log_state),

/// 获取设备的日志状态
libManager.send(evt: CmdEvtType.getDeviceLogState, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明                                                     |
| -------- | -------- | ------------------------------------------------------------ |
| type     | int      | 0：没有对应的日志产生  <br />1：固件重启log（100- 200）<br />2：固件异常（0-100） |
| err_code | int      | 固件重启log错误码  0正常                                     |

`示例：`

```c
{
  "err_code":4,
  "type":1
}
```

