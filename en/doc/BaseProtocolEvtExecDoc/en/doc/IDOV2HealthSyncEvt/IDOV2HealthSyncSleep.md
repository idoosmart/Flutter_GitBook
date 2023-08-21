#### Sync Sleep Data


**JSON Fields Received by the App:**

| Field Name         | Field Type | Field Description                                   |
| ------------------ | ---------- | -------------------------------------------------- |
| year               | int        | Data date - Year                                    |
| month              | int        | Data date - Month                                   |
| day                | int        | Data date - Day                                     |
| end_time_hour      | int        | Sleep end time - Hour                               |
| end_time_minute    | int        | Sleep end time - Minute                             |
| total_minute       | int        | Total sleep time in minutes                          |
| light_sleep_count  | int        | Number of light sleep phases                         |
| deep_sleep_count   | int        | Number of deep sleep phases                          |
| wake_count         | int        | Number of wake-up events                             |
| light_sleep_minute | int        | Total duration of light sleep in minutes             |
| deep_sleep_minute  | int        | Total duration of deep sleep in minutes              |
| sleep_score        | int        | Sleep score                                          |
| items              | Array      | Sleep details: durations and sleep_status for each phase |

| Field Name        | Field Type | Field Description                        |
| ----------------- | ---------- | --------------------------------------- |
| durations         | int        | Duration of sleep phase in minutes       |
| sleep_status      | int        | Sleep status:<br />1: Awake<br />2: Light Sleep<br />3: Deep Sleep<br />4: REM Sleep |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 23,
    "end_time_hour": 20,
    "end_time_minute": 0,
    "total_minute": 30,
    "light_sleep_count": 3,
    "deep_sleep_count": 1,
    "wake_count": 1,
    "light_sleep_minute": 22,
    "deep_sleep_minute": 8,
    "sleep_score": 75,
    "items": [
        {
            "durations": 5,
            "sleep_status": 1
        },
        {
            "durations": 10,
            "sleep_status": 2
        },
        {
            "durations": 10,
            "sleep_status": 2
        },
        {
            "durations": 2,
            "sleep_status": 2
        },
        {
            "durations": 8,
            "sleep_status": 3
        }
    ]
}
```