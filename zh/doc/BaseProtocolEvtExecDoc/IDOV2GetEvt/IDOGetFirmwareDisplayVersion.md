### 获取固件显示版本号

功能表：`supportGetFirmwareDisplayVersion`

**Flutter 示例：**

```dart
libManager.send(evt: CmdEvtType.getFirmwareDisplayVersion, json: jsonEncode({}));
```

**App 收到的 json 字段：**

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| err_code | int | `0`：成功；其他：失败 |
| display_version | string | 固件 UI 显示版本号，如 `"1_00_09"` |

`示例：`

```json
{
  "err_code": 0,
  "display_version": "1_00_09"
}
```

**注意事项：**

- 下发前建议判断 `libManager.funTable.supportGetFirmwareDisplayVersion`。
