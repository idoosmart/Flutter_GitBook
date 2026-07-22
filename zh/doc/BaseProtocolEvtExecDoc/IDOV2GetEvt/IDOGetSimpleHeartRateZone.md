### 获取简单心率区间设置

功能表: supportSimpleHrZoneSetting

**Flutter example:**

```dart
/// 获取简单心率区间设置
getSimpleHeartRateZone(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_app_get_simple_heart_rate_zone),

/// 获取简单心率区间设置
libManager.send(evt: CmdEvtType.getSimpleHeartRateZone, json: jsonEncode(json));
```


**JSON fields received by App**:

| Field name | Field type | Field description |
| ------ | -------- | ---------------------------- |
| max_hr_value | int | Maximum heart rate during exercise |

`Example:`

```c
{
"max_hr_value":190,
}
```