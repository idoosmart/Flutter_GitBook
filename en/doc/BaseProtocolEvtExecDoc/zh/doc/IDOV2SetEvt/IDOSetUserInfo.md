### 设置用户信息


**Flutter示例：**

```dart
/// 设置用户信息事件号
setUserInfo(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_user_info),

/// 设置用户信息
libManager.send(evt: CmdEvtType.setUserInfo, json: jsonEncode(json));
```



**App下发的json字段**：

| 字段名 | 字段类型 | 字段说明                        |
| ------ | -------- | ------------------------------- |
| year   | int      | 出生日期 年                     |
| month  | int      | 出生日期 月                     |
| day    | int      | 出生日期 日                     |
| hour   | int      | 出生日期 时                     |
| height | int      | 身高 单位厘米                   |
| weight | int      | 体重 单位千克 值需要x100
| gender | int      | 性别<br />1：女 <br />0：男 |

`示例：`

```c
{
  "year":2022,
  "monuth":12,
  "day":16,
  "hour":18,
  "heigh":173,
  "weigh":74,
  "gender":0
}
```

