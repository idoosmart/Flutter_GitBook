### V3 Get GPS Data for a Certain Period in Data Exchange

**Flutter Example:**

```dart
/// V3 Get GPS Data for a Certain Period in Data Exchange event number
getActivityExchangeGpsData(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.func_v3_get_activity_exchange_gps_data),

/// V3 Get GPS Data for a Certain Period in Data Exchange
libManager.send(evt: CmdEvtType.getActivityExchangeGpsData, json: jsonEncode(json));
```

**JSON fields received by the app**:

| Field Name      | Field Type | Field Description               |
| --------------- | ---------- | ------------------------------- |
| version         | int        | Protocol version number         |
| hour            | int        | Hour                            |
| minute          | int        | Minute                          |
| second          | int        | Second                          |
| interval_second | int        | Interval time in seconds        |
| GPS_data_len    | int        | Length of GPS data              |
| GPS_data        | List       | List of GPS data details        |

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| latitude   | double     | Latitude          |
| longitude  | double     | Longitude         |

**Example:**

```json
{
  "version": 0,
  "hour": 0,
  "minute": 0,
  "second": 0,
  "interval_second": 0,
  "GPS_data_len": 1,
  "GPS_data": [
    {
      "latitude": 0,
      "longitude": 0
    }
  ]
}
```
