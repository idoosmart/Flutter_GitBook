### Set ALEXA notification status in the app

Menu: getVoiceTransmission

**JSON fields sent by the app**:

| Field Name   | Field Type | Field Description                                         |
| ------------ | ---------- | -------------------------------------------------------- |
| notify_flag  | int        | 0: Invalid value<br/>1: Notification present (yellow)<br/>2: Clear notification (blue) |

`Example:`

```json
{
    "notify_flag": 0
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

将文本中的中文转英文，其他结构不要改变。