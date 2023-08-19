### 设置寻找手机


功能表: getFindPhone

**Flutter示例：**

```dart
/// 设置寻找手机
setFindPhone(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_find_phone),

/// 设置勿扰模式
libManager.send(evt: CmdEvtType.setNotDisturb, json: jsonEncode(json));
```



**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明               |
| ------ | -------- | ---------------------- |
| on_off | int      | 170：打开， 85:关闭 |

`示例：`

```c
{
  "on_off":0
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

