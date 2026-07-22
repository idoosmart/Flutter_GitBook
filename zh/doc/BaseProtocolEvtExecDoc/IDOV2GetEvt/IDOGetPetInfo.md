### 获取宠物信息

功能表：supportPetInfo

**Flutter示例：**

```dart
/// 获取宠物信息事件号
/// getPetInfo(
///   evtBase: _VBusEvtBase.base_app_get,
///   evtType: _VBusEvtType.app_get_pet_info),

libManager.send(evt: CmdEvtType.getPetInfo, json: jsonEncode({}));
```

**App收到的json字段**：

| 字段名   | 字段类型 | 字段说明 |
| -------- | -------- | -------- |
| pet_type | int      | 宠物类型：0无效，1猫，2狗 |
| weight   | int      | 体重x100，单位kg |
| gender   | int      | 性别：0公，1母 |
| year     | int      | 生日年 |
| month    | int      | 生日月 |
| day      | int      | 生日日 |

`示例：`

```json
{
  "pet_type": 1,
  "weight": 450,
  "gender": 0,
  "year": 2024,
  "month": 1,
  "day": 1
}
```

**注意事项：**

- 下发前建议先判断功能表 `libManager.funTable.supportPetInfo`。
