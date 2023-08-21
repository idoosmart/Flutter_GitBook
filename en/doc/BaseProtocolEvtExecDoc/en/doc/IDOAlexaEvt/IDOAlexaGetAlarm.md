### V3ALEXA Get Alarms


Function ID: alexaSetGetAlexaAlarmV3

**JSON fields received by the App**:

| Field Name | Field Type | Field Description                                  |
| ---------- | ---------- | -------------------------------------------------- |
| version    | int        | Protocol version number                            |
| item       | array      | Array of alarm details, including alarm_id, status, year, month, day, hour, minute, and repeat |

| Field Name | Field Type | Field Description                                                |
| ---------- | ---------- | ---------------------------------------------------------------- |
| alarm_id   | int        | Alarm ID                                                          |
| status     | int        | 170 to hide (delete) the alarm, 85 to show the alarm              |
| year       | int        | Year                                                              |
| month      | int        | Month                                                             |
| day        | int        | Day                                                               |
| hour       | int        | Hour                                                              |
| minute     | int        | Minute                                                            |
| repeat     | int        | Repeat schedule: bit1-bit7 for Monday to Sunday, bit0 as the switch |

`Example:`

```json
{
    "version": 0,
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