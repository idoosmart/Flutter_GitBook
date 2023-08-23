### 下发绑定码绑定(内部使用)


功能表: getBindCodeAuth

**Flutter示例：**

```dart
/// 绑定码绑定事件号
setAuthCode(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_auth),

/// 绑定码绑定
libManager.send(evt: CmdEvtType.setAuthCode, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名        | 字段类型 | 字段说明                                 |
| ------------- | -------- | ---------------------------------------- |
| is_clean_data | int      | 1：清除<br />其他 ：无效              |
| os_type       | int      | 系统<br />1：ios，<br />2：android |
| os_version    | int      | 系统版本号                               |
| auth_length   | int      | 绑定码长度 最大值8                       |
| auth_code     | int [ ]  | 绑定码内容                               |

`示例：`

```c
{
  "is_clean_data":0,
  "os_type":1,
  "os_version":0,
  "auth_length":6,
  "auth_code":
  [
    1,
    2,
    3,
    4,
    5,
    6
  ]
}

```

**App收到的json字段**：

| 字段名        | 字段类型 | 字段说明                                                     |
| ------------- | -------- | ------------------------------------------------------------ |
| auth_ret_code | int      | 状态<br />0：成功 <br />1：失败<br />2：绑定码丢失失败 |

`示例：`

```c
{
  "auth_ret_code":0
}
```