# V3 Algorithm Raw Data Switch

function table: supportAlgorithmRawDataCollect

### Description
Event ID: 5105

Control the device to upload raw algorithm data, primarily for debugging or specialized algorithm research.

### Commands to be executed
`CmdEvtType.setAlgorithmRawData`

### Flutter Example
```dart
final jsonStr = jsonEncode({
  "on_off": 1, 
  "type": 1    
});
IDOWaitEvt(CmdEvtType.setAlgorithmRawData).then((value) {
  // handle response
});
IDOProtocolNative.instance.sendDataToBle(
  jsonStr,
  CmdEvtType.setAlgorithmRawData.index
);
```

### JSON Structure Description (Set by App)
| Field Name | Type | Unit | Range | Description |
| :--- | :--- | :--- | :--- | :--- |
| on_off | int | - | 0/1 | Raw data upload switch |
| type | int | - | - | Algorithm type (refer to protocol_c definition) |

### C-Struct Parameter Description
```c
/**
 * @struct protocol_set_v3_algorithm_raw_data
 * @brief Set V3 algorithm raw data
 */
struct protocol_set_v3_algorithm_raw_data
{
    uint8_t on_off;      // raw data switch
    uint8_t type;        // algorithm type
};
```

### JSON Sample (Set by App)
```json
{
  "on_off": 1,
  "type": 1
}
```
