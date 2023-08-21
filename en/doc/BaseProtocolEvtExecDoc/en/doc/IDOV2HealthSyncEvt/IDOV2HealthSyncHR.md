#### Sync Heart Rate Data


**JSON Fields Received by the App:**

| Field Name            | Field Type | Field Description                                      |
| --------------------- | ---------- | ----------------------------------------------------- |
| year                  | int        | Data date - Year                                       |
| month                 | int        | Data date - Month                                      |
| day                   | int        | Data date - Day                                        |
| start_time            | int        | Offset from 0:00 for the data in minutes               |
| silent_heart_rate     | int        | Resting heart rate                                     |
| burn_fat_threshold    | int        | Heart rate threshold for fat burning                    |
| aerobic_threshold     | int        | Heart rate threshold for aerobic exercise              |
| limit_threshold       | int        | Heart rate threshold for maximum exercise              |
| burn_fat_mins         | int        | Duration of fat burning heart rate, in minutes         |
| aerobic_mins          | int        | Duration of aerobic exercise, in minutes               |
| limit_mins            | int        | Duration of maximum exercise, in minutes               |
| warm_up_threshold     | int        | Heart rate threshold for warm up exercise              |
| warm_up_mins          | int        | Duration of warm up exercise, in minutes               |
| anaerobic_threshold   | int        | Heart rate threshold for anaerobic exercise            |
| anaerobic_mins        | int        | Duration of anaerobic exercise, in minutes             |
| items                 | Array      | Heart rate details: offset_minute and heart_rate_value |

| Field Name            | Field Type | Field Description                                      |
| --------------------- | ---------- | ----------------------------------------------------- |
| offset_minute         | int        | Offset of the data in minutes, used for time alignment |
| heart_rate_value      | int        | Heart rate value                                      |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 23,
    "start_time": 0,
    "silent_heart_rate": 80,
    "burn_fat_threshold": 0,
    "aerobic_threshold": 0,
    "limit_threshold": 0,
    "burn_fat_mins": 0,
    "aerobic_mins": 0,
    "limit_mins": 0,
    "warm_up_threshold": 0,
    "warm_up_mins": 0,
    "anaerobic_threshold": 0,
    "anaerobic_mins": 0,
    "items": [
        {
            "offset_minute": 5,
            "heart_rate_value": 90
        },
        {
            "offset_minute": 5,
            "heart_rate_value": 80
        },
        {
            "offset_minute": 5,
            "heart_rate_value": 85
        }
    ]
}
```