### Set recognized status in the app

Menu: getVoiceTransmission

**JSON fields sent by the app**:

| Field Name   | Field Type | Field Description                                   |
| ------------ | ---------- | -------------------------------------------------- |
| phone_state  | int        | 0: Normal state<br/>1: Unable to recognize<br/>2: Voice recognition timeout |

`Example:`

```json
{
    "phone_state": 0
}
```

**JSON fields returned by the app**:

| Field Name   | Field Type | Field Description |
| ------------ | ---------- | ----------------- |
| is_success   | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```
