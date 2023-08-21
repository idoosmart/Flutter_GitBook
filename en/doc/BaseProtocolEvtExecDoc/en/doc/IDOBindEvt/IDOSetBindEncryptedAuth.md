### Send Calculated Authorization Data (Internal Use)


Function: exTableMain8EncryptedAuth (SDK to be supplemented)

**Flutter Example:**

```dart
/// Event number for sending calculated authorization data
setEncryptedAuth(
  evtBase: _VBusEvtBase.base_app_set,
  evtType: _VBusEvtType.app_set_encrypted_auth),

/// Send calculated authorization data
libManager.send(evt: CmdEvtType.setEncryptedAuth, json: jsonEncode(json));
```



**JSON fields sent by the app**:

| Field Name         | Field Type | Field Description                             |
| ------------------ | ---------- | --------------------------------------------- |
| encrypted_version  | int        | Encryption method version: 0 (original), 16 (new) |
| auth_length        | int        | Length of the key data                        |
| autu_data          | int [ ]    | Authorization data, maximum 12 bytes           |

`Example:`

```json
{
  "encrypted_version": 1,
  "auth_length": 12,
  "autu_data":
  [
    1,
    2,
    3,
    4,
    5,
    6,
    7,
    8,
    9,
    10,
    11,
    12
  ]
}
```

**JSON fields returned by the app**:

| Field Name          | Field Type | Field Description                                   |
| ------------------- | ---------- | -------------------------------------------------- |
| auth_code           | int        | Authorization result: 0 (success), non-zero (failure)  |
| encrypted_version   | int        | Encryption method version: 0 (original), 16 (new) |

`Example:`

```json
{
  "auth_code": 2,
  "encrypted_version": 0
}
```
