### ~~Get Device Name~~


Menu: TODO

**Flutter Example:**

```dart
/// Get device name event number
getDeviceName(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_devices_name),

/// Get device name
libManager.send(evt: CmdEvtType.getDeviceName, json: jsonEncode(json));
```



**JSON fields received by the App**:

| Field Name  | Field Type  | Field Description                                           |
| ----------- | ----------- | ----------------------------------------------------------- |
| is_success  | int         | 1: Success, 0: Failure                                      |
| dev_name    | char [16]   | Success: The current name stored in the firmware, the name set successfully if returned |

`Example:`

```c
{
  "is_success": 1,
  "dev_name": "ID208BT"
}
```