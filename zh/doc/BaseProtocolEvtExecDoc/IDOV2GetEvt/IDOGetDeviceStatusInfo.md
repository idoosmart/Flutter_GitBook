### 获取设备状态（GET:0x02/0x49）

功能表：`supportGetDeviceStatus`、`supportGetDeviceSportStatus`

**Flutter 示例：**

```dart
/// 获取设备状态
libManager.send(
  evt: CmdEvtType.getDeviceStatusInfo,
  json: jsonEncode({'get_type': 1}),
);
// 可省略 get_type，协议库默认查询 bit0（运动状态）
```

**App 收到的 json 字段：**

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| get_type | int | 回显查询掩码 |
| has_sport_start_type | bool | 是否包含运动状态 |
| sport_start_type | int | `0` 未运动；`1` App 发起运动中；`2` 手表发起；`3` 自识别运动中 |

`示例：`

```json
{
  "get_type": 1,
  "has_sport_start_type": true,
  "sport_start_type": 1
}
```

**注意事项：**

- 事件号 `361`；下发前建议判断 `libManager.funTable.supportGetDeviceStatus`。
- 查询运动状态子项需 `supportGetDeviceSportStatus == true`。
