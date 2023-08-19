### APP通知固件某些功能的权限状态


**Flutter示例：**

```dart
/// app被禁用功能权限导致某些功能无法启用，同时需要告知固件改功能已被禁用
setNoticeDisableFunc(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_app_to_ble_notcie_disable_func
),

/// app被禁用功能权限导致某些功能无法启用，同时需要告知固件改功能已被禁用
libManager.send(evt: CmdEvtType.setNoticeDisableFunc, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明                    |
| ------ | -------- | --------------------------- |
| type   | int      | 0：相机权限              |
| enable | int      | 170：启用 <br />85：关闭 |

`示例：`

```c
{
    "type":0,
    "enable":85
}
```

**App收到的json字段**：

| 字段名      | 字段类型 | 字段说明                     |
| ----------- | -------- | ---------------------------- |
| status_code | int      | 成功：0  <br />失败：1 |

`示例：`

```c
{
    "status_code":0
}
```
