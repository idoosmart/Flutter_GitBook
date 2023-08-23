### 发送计算好的授权数据(内部使用)


功能表:exTableMain8EncryptedAuth(SDK待补充)

**Flutter示例：**

```dart
/// 发送计算好的授权数据事件号
setEncryptedAuth(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_encrypted_auth),

/// 发送计算好的授权数据
libManager.send(evt: CmdEvtType.setEncryptedAuth, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名            | 字段类型 | 字段说明                                       |
| ----------------- | -------- | ---------------------------------------------- |
| encrypted_version | int      | 加密方式版本 原有的是0<br />新的加密版本是16 |
| auth_length       | int      | 密钥数据长度                                   |
| autu_data         | int [] | 授权数据 最大12个字节                          |

`示例：`

```c
{
  "encrypted_version":1,
  "auth_length":12,
  "autu_data":
  [
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11,
    12
  ]
}
```

**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                                     |
| ----------------- | -------- | ------------------------------------------------------------ |
| auth_code         | int      | 授权结果 <br />0：成功 , 非0失败<br />1：是手表点击拒绝<br />2：密码校验失败或者已经绑定 |
| encrypted_version | int      | 加密方式版本 原有的是0<br />新的加密版本是16               |

`示例：`

```c
{
  "auth_code":2,
  "encrypted_version":0
}
```

