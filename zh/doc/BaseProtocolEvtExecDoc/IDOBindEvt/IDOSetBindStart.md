### 设置绑定(内部使用)


功能表: BindAuth(SDK待补充)

**Flutter示例：**

```dart
/// 绑定事件号
setBindStart(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_bind_start),

/// 绑定
libManager.send(evt: CmdEvtType.setBindStart, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名        | 字段类型 | 字段说明                               |
| ------------- | -------- | -------------------------------------- |
| is_clean_data | int      | 1：清除<br />其他 ：无效            |
| os_type       | int      | 系统<br />1：ios<br />2：android |
| os_version    | int      | 系统版本号                             |
| bind_version  | int      | 绑定策略版本号 从1 开始             |

`示例：`

```c
{
  "is_clean_data":0,
  "os_type":2,
  "os_version":0,
  "bind_version":0
}
```



**App收到的json字段**：

| 字段名            | 字段类型 | 字段说明                                   |
| ----------------- | -------- | ------------------------------------------ |
| auth_length       | int      | 0表示不支持                                |
| bind_ret_code     | int      | 0表示成功,1表示失败,2表示已经绑定          |
| encrypted_version | int      | 加密方式版本 原有的是0；新的加密版本是16 |
| encrypted_data    | char []   | 加密数据 固件生成 12个字节大小             |

`示例：`

```c
{
  "auth_length":0,
  "bind_ret_code":0
}
```

