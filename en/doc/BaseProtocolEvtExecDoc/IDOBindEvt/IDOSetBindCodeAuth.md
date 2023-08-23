### Bind Code Binding (Internal Use)


Function: getBindCodeAuth

**Flutter Example:**

```dart
/// Bind Code Binding Event Number
setAuthCode(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_auth),

/// Bind Code Binding
libManager.send(evt: CmdEvtType.setAuthCode, json: jsonEncode(json));
```



**JSON fields sent by the app**:

| Field Name    | Field Type | Field Description                           |
| ------------- | ---------- | ------------------------------------------- |
| is_clean_data | int        | 1: Clear<br />Other: Invalid                 |
| os_type       | int        | Operating system<br />1: iOS,<br />2: Android |
| os_version    | int        | Operating system version                     |
| auth_length   | int        | Length of the binding code, maximum value: 8 |
| auth_code     | int [ ]    | Content of the binding code                   |

`Example:`

```json
{
  "is_clean_data": 0,
  "os_type": 1,
  "os_version": 0,
  "auth_length": 6,
  "auth_code":
  [
    1,
    2,
    3,
    4,
    5,
    6
  ]
}
```

**JSON fields returned by the app**:

| Field Name     | Field Type | Field Description                                |
| -------------- | ---------- | ------------------------------------------------- |
| auth_ret_code  | int        | Status<br />0: Success<br />1: Failure<br />2: Failed to bind code |

`Example:`

```json
{
  "auth_ret_code": 0
}
```
