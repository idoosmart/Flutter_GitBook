### 简单心率区间设置

**Flutter示例：**

```dart
/// 简单心率区间设置事件号
setSimpleHeartRateZone(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.vbus_evt_app_set_simple_heart_rate_zone),

/// 简单心率区间设置
libManager.send(evt: CmdEvtType.setSimpleHeartRateZone, json: jsonEncode(json));
```

**App下发的json字段**:

| 字段名 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| max_hr_value | int | 运动中最大心率值 |

`示例：`

```json
{
    "max_hr_value": 180
}
```

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| err_code | int | 错误码：0为成功，非0为失败 |

`示例：`

```json
{
    "err_code": 0
}
```
