### 获取简单心率区间设置

**Flutter示例：**

```dart
/// 获取简单心率区间设置事件号
getSimpleHeartRateZone(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.vbus_evt_app_get_simple_heart_rate_zone),

/// 获取简单心率区间设置
libManager.send(evt: CmdEvtType.getSimpleHeartRateZone);
```

**App下发的json字段**:
无参数

**App收到的json字段**：

| 字段名 | 字段类型 | 字段说明 |
| :--- | :--- | :--- |
| max_hr_value | int | 运动中最大心率值 |

`示例：`

```json
{
    "max_hr_value": 180
}
```
