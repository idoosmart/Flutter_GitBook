### 获取设备升级状态


功能表:getDeviceUpdateState

**Flutter示例：**

```dart
/// 获取设备升级状态事件号
getUpdateStatus(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_update_state),

/// 获取设备升级状态
libManager.send(evt: CmdEvtType.getUpdateStatus, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                     |
| ---------- | -------- | ---------------------------- |
| dev_vesion | int      | 固件版本号                   |
| state      | int      | 0是正常状态<br />1是升级状态 |

`示例：`

```c
{
  "dev_vesion":0,
  "state":0
}
```

