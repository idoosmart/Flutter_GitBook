### 获取寻找手机开关状态（GET:0x02/0x26）

功能表：`supportGetFindPhoneSwitch`（`support_get_find_phone_switch`）

**Flutter 示例：**

```dart
libManager.send(evt: CmdEvtType.getFindPhoneSwitch, json: jsonEncode({}));
```

**App 收到的 json 字段：**

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| onOff  | bool     | 开：`true`（`0xAA`）；关：`false`（`0x55`） |

`示例：`

```json
{"onOff": true}
```

**注意事项：**

- 下发前建议先判断功能表 `libManager.funTable.supportGetFindPhoneSwitch`。
