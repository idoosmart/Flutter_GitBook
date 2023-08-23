### ~~Device Notification to App for Operation Type~~

**JSON fields received by the App**:

| Field Name | Type | Description                              |
| ---------- | ---- | ---------------------------------------- |
| timeout    | int  | Timeout duration in seconds              |
| type       | int  | Operation type: 1 for short press, 2 for long press, 3 for tap, 4 for double tap |

`Example`:

```json
{
    "timeout": 30,
    "type": 1
}
```
