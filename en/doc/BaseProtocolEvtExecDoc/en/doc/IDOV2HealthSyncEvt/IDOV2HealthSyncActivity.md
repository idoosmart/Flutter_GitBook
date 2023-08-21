#### Synchronize Activity (Multi-Sport) Data

**JSON Fields Sent by the App:**

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
|            |            |                   |

**JSON Fields Received by the App:**

| Field Name                | Field Type | Field Description             |
| ------------------------- | ---------- | ----------------------------- |
| year                      | int        | Year                          |
| month                     | int        | Month                         |
| day                       | int        | Day                           |
| hour                      | int        | Hour                          |
| minute                    | int        | Minute                        |
| second                    | int        | Second                        |
| data_length               | int        | Data length                   |
| hr_data_interval_minute   | int        | Heart rate data interval       |
| hr_item_count             | int        | Number of heart rate readings  |
| packet_count              | int        | Packet count                  |
| type                      | int        | Sport type                    |
| step                      | int        | Steps/Count                   |
| durations                 | int        | Duration                      |
| calories                  | int        | Calories                      |
| distance                  | int        | Distance                      |
| avg_hr_value              | int        | Average heart rate             |
| max_hr_value              | int        | Maximum heart rate             |
| burn_fat_mins             | int        | Fat-burning time               |
| aerobic_mins              | int        | Aerobic exercise time          |
| limit_mins                | int        | Limit exercise time            |
| range1                    | int        | Warm-up exercise accumulated time (in minutes)         |
| range2                    | int        | Fat-burning exercise accumulated time (in minutes)      |
| range3                    | int        | Aerobic exercise accumulated time (in minutes)         |
| range4                    | int        | Anaerobic exercise accumulated time (in minutes)       |
| range5                    | int        | Limit exercise accumulated time (in minutes)          |
| hr_data_vlaue             | int []     | Heart rate data details<br />Maximum of 68,535 values |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "hour": 10,
    "minute": 38,
    "second": 20,
    "data_length": 10,
    "hr_data_interval_minute": 5,
    "hr_item_count": 10,
    "packet_count": 1,
    "type": 1,
    "step": 200,
    "durations": 10,
    "calories": 50,
    "distance": 200,
    "avg_hr_value": 85,
    "max_hr_value": 90,
    "burn_fat_mins": 0,
    "aerobic_mins": 0,
    "limit_mins": 0,
    "range1": 0,
    "range2": 0,
    "range3": 0,
    "range4": 0,
    "range5": 0,
    "hr_data_vlaue": [
        85,
        87,
        90,
        93,
        91,
        80,
        90,
        81,
        83,
        86
    ]
}
```