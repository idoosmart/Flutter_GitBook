# V3 Blood Glucose Data Upload/Query

function table: supportBloodGlucose

### Description
Event ID: 5104

Upload or query blood glucose information, specifically used for the continuous monitoring and data synchronization of blood glucose.

### Commands to be executed
`CmdEvtType.setGlucoseInformation`

### Flutter Example
```dart
final jsonStr = jsonEncode({
  "on_off": 1,
  "unit": 1,
  "glucose_value": 5.5,
  "collect_time": 1711852800 
});
IDOWaitEvt(CmdEvtType.setGlucoseInformation).then((value) {
  // handle response
});
IDOProtocolNative.instance.sendDataToBle(
  jsonStr,
  CmdEvtType.setGlucoseInformation.index
);
```

### JSON Structure Description (Set by App)
| Field Name | Type | Unit | Range | Description |
| :--- | :--- | :--- | :--- | :--- |
| on_off | int | - | 0/1 | Blood glucose reminder/upload switch |
| unit | int | - | - | Blood glucose unit (0: mg/dL, 1: mmol/L) |
| glucose_value | float | - | - | Blood glucose value |
| collect_time | int | s | - | Collection time (Unix timestamp) |

### C-Struct Parameter Description
```c
/**
 * @brief Set glucose information
 * @struct protocol_set_glucose_information
 */
struct protocol_set_glucose_information
{
    uint8_t on_off;         // blood glucose switch
    uint8_t unit;           // blood glucose unit
    float glucose_value;     // blood glucose value
    uint32_t collect_time;  // collection time
};
```

### JSON Sample (Set by App)
```json
{
  "on_off": 1,
  "unit": 1,
  "glucose_value": 5.5,
  "collect_time": 1711852800
}
```
