### Set reminders for V3 voice settings

Menu: getVoiceTransmission

**JSON fields sent by the app**:

| Field Name        | Field Type | Field Description                                                |
| ----------------- | ---------- | --------------------------------------------------------------- |
| item              | Array      | Collection of reminder_id, status, year, month, day, hour, minute, and reminder_string |

| Field Name        | Field Type | Field Description                                  |
| ----------------- | ---------- | ------------------------------------------------- |
| reminder_id       | int        | ID from 1 to 5                                     |
| status            | int        | Switch status: 170 to turn off, 85 to turn on      |
| year              | int        | Year                                               |
| month             | int        | Month                                              |
| day               | int        | Day                                                |
| hour              | int        | Hour                                               |
| minute            | int        | Minute                                             |
| sec               | int        | Second (requires support for key: V3_alexa_reminder_add_sec) |
| reminder_string   | char[]     | Reminder content (maximum 128 bytes)               |

`Example:`

```json
{
    "item": [
        {
            "reminder_id": 1,
            "status": 85,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 12,
            "minute": 30,
            "sec": 30,
            "reminder_string": "Remember to eat"
        },
        {
            "reminder_id": 2,
            "status": 85,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 23,
            "minute": 30,
            "sec": 30,
            "reminder_string": "Remember to sleep"
        },
        {
            "reminder_id": 3,
            "status": 85,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 20,
            "minute": 00,
            "sec": 30,
            "reminder_string": "Remember to take a bath"
        },
        {
            "reminder_id": 4,
            "status": 85,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 8,
            "minute": 0,
            "sec": 30,
            "reminder_string": "Remember to wake up"
        },
        {
            "reminder_id": 5,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 14,
            "minute": 0,
            "sec": 30,
            "reminder_string": ""
        }
    ]
}
```

**JSON fields returned by the app**:

| Field Name        | Field Type | Field Description |
| ----------------- | ---------- | ----------------- |
| is_success        | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```
