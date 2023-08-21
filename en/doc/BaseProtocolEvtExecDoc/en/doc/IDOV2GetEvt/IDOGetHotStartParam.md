### ~~Get Hot Start Parameters~~

Function Table: getSupportUpdateGps

**Flutter Example:**

```dart
/// Get Hot Start Parameters event number
getHotStartParam(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_hot_start_param),

/// Get Hot Start Parameters
libManager.send(evt: CmdEvtType.getHotStartParam, json: jsonEncode(json));
```



**JSON Fields Received by the App**:

| Field Name    | Field Type | Description                        |
| ------------- | ---------- | ---------------------------------- |
| tcxo_offset   | int        | TCXO offset                        |
| longitude     | int        | Longitude (multiplied by 10^6)     |
| latitude      | int        | Latitude (multiplied by 10^6)      |
| altitude      | int        | Altitude (multiplied by 10)        |

`Example:`

```c
{
    "tcxo_offset":0,
    "longitude":0,
    "latitude":0,
    "altitude":0
}
```