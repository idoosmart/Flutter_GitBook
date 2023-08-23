### Device Get App Login State


**JSON fields sent by the App**:

| Field Name | Field Type | Field Description                                            |
| ---------- | ---------- | ------------------------------------------------------------ |
| log_state  | int        | 0: Normal state (logged in)<br />1: Not logged in<br />2: Network disconnected<br />3: State not obtained |

`Example:`

```json
{
    "log_state": 0
}
```