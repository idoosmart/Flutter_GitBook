### V3 Get 1 Minute Heart Rate Data in Data Exchange

**Flutter Example:**

```dart
/// Event number for app to get V3 heart rate data
exchangeAppGetV3HrData(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_activity_exchange_heart_rate_data),

/// App gets V3 heart rate data
libManager.send(evt: CmdEvtType.exchangeAppGetV3HrData, json: jsonEncode(json));
```

**JSON fields received by the app**:

| Field Name            | Field Type | Field Description                        |
| --------------------- | ---------- | ---------------------------------------- |
| version               | int        | Protocol version number (reserved)       |
| hour                  | int        | Hour                                     |
| minute                | int        | Minute                                   |
| second                | int        | Second                                   |
| heart_rate_history_len | int        | Length of heart rate data array (max 60)  |
| interval_second       | int        | Heart rate interval in seconds           |
| heart_rate_history    | List<int>  | Heart rate data array for one minute, with one data point every second |

**Example:**

```json
{
  "version": 0,
  "hour": 0,
  "minute": 0,
  "second": 0,
  "heart_rate_history_len": 0,
  "interval_second": 0,
  "heart_rate_history": [
    85,
    85,
    86,
    90,
    100,
    80,
    75
  ]
}
```
