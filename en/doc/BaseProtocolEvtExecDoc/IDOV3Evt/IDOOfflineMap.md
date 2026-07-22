# V3 Offline Map Operation

function table: supportOfflineMapInformation

### Description
Event ID: 5109

Support offline map management for the device, such as packet transmission, installation and deletion.

### Commands to be executed
`CmdEvtType.setOfflineMap`

### Flutter Example
```dart
// Action: 0-Init, 1-Update, 2-Delete (refer to protocol_c for details)
final action = 0;
final jsonStr = jsonEncode({
  "on_off": 1,
  "action": action
});
IDOWaitEvt(CmdEvtType.setOfflineMap).then((value) {
  // handle response
});
IDOProtocolNative.instance.sendDataToBle(
  jsonStr,
  CmdEvtType.setOfflineMap.index
);
```

### JSON Structure Description (Set by App)
| Field Name | Type | Unit | Range | Description |
| :--- | :--- | :--- | :--- | :--- |
| on_off | int | - | 0/1 | Offline map function switch |
| action | int | - | - | Operation action (0: Init, 1: Update, 2: Delete) |

### C-Struct Parameter Description
```c
/**
 * @struct protocol_set_v3_offline_map
 * @brief Set V3 offline map
 */
struct protocol_set_v3_offline_map
{
    uint8_t on_off;      // functional switch
    uint8_t action;      // map action
};
```

### JSON Sample (Set by App)
```json
{
  "on_off": 1,
  "action": 0
}
```
