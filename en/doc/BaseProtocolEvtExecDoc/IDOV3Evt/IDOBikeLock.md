# V3 Bike Lock Operation

function table: supportBikeLockManager

### Description
Event ID: 5107

Perform smart bike lock control, including locking, unlocking and state querying.

### Commands to be executed
`CmdEvtType.setBikeLock`

### Flutter Example
```dart
// Action: 0-Lock, 1-Unlock, 2-State Query
final action = 0;
final jsonStr = jsonEncode({
  "on_off": 1,
  "action": action
});
IDOWaitEvt(CmdEvtType.setBikeLock).then((value) {
  // handle response
});
IDOProtocolNative.instance.sendDataToBle(
  jsonStr,
  CmdEvtType.setBikeLock.index
);
```

### JSON Structure Description (Set by App)
| Field Name | Type | Unit | Range | Description |
| :--- | :--- | :--- | :--- | :--- |
| on_off | int | - | 0/1 | Bike lock function switch |
| action | int | - | - | Operation action (0: Lock, 1: Unlock, 2: State query) |

### C-Struct Parameter Description
```c
/**
 * @struct protocol_set_v3_bike_lock
 * @brief Set V3 bike lock
 */
struct protocol_set_v3_bike_lock
{
    uint8_t on_off;      // functional switch
    uint8_t action;      // lock action
};
```

### JSON Sample (Set by App)
```json
{
  "on_off": 1,
  "action": 0
}
```
