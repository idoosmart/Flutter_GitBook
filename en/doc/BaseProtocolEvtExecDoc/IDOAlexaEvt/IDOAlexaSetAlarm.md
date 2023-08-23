### Set alarm clock via V3 voice

**JSON fields sent by the App**:

| Field Name | Field Type | Field Description                                                |
| ---------- | ---------- | ---------------------------------------------------------------- |
| item       | array      | An array of alarm_id, status, year, month, day, hour, and minute |

| Field Name | Field Type | Field Description                                                |
| ---------- | ---------- | ---------------------------------------------------------------- |
| alarm_id   | int        | The ID of the alarm clock (1-10)                                 |
| status     | int        | The switch status<br />170: Off<br />85: On                     |
| year       | int        | The year                                                        |
| month      | int        | The month                                                       |
| day        | int        | The day                                                         |
| hour       | int        | The hour                                                        |
| minute     | int        | The minute                                                      |
| repeat     | int        | The repeat setting<br />bit1-bit7: Monday to Sunday<br />bit0 is the master switch (On/Off)<br />Requires support from the menu, key: V3_alexa_set_get_alexa_alarm |

`Example:`

```json
{
    "item": [
        {
            "alarm_id": 1,
            "status": 85,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 14,
            "minute": 54,
            "repeat": 127
        },
        {
            "alarm_id": 2,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 15,
            "minute": 54,
            "repeat": 127
        },
        {
            "alarm_id": 3,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 16,
            "minute": 54,
            "repeat": 127
        },
        {
            "alarm_id": 4,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 20,
            "minute": 54,
            "repeat": 127
        },
        {
            "alarm_id": 5,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 22,
            "minute": 54,
            "repeat": 127
        },
        {
            "alarm_id": 6,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 26,
            "hour": 23,
            "minute": 0,
            "repeat": 127
        },
        {
            "alarm_id": 7,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 8,
            "minute": 0,
            "repeat": 127
        },
        {
            "alarm_id": 8,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 14,
            "minute": 0,
            "repeat": 127
        },
        {
            "alarm_id": 9,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 15,
            "minute": 20,
            "repeat": 127
        },
        {
            "alarm_id": 10,
            "status": 170,
            "year": 2022,
            "month": 12,
            "day": 27,
            "hour": 15,
            "minute": 30,
            "repeat": 127
        }
    ]
}
```

**JSON fields returned by the App**:

| Field Name   | Field Type | Field Description            |
| ------------ | ---------- | ---------------------------- |
| is_success   | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```