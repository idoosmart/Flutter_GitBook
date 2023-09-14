## Device Notification to Start One-Click Call in App

**JSON fields received by the App**:

| Field Name | Type | Description                                          |
| ---------- | ---- | ---------------------------------------------------- |
| status     | int  | Status: 0 for start, 1 for end                       |
| timeout    | int  | Timeout duration in seconds                           |

`Example`:

```json
{
    "status": 0,
    "timeout": 30
}
```

