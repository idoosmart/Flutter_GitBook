### Get Simple heart rate zone setting

Function table: supportSimpleHrZoneSetting

**Flutter example:**

```dart
/// Get Simple heart rate zone setting
getSimpleHeartRateZone(
evtBase: _VBusEvtBase.base_app_set,
evtType: _VBusEvtType.vbus_evt_app_get_simple_heart_rate_zone),

/// Get Simple heart rate zone setting
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