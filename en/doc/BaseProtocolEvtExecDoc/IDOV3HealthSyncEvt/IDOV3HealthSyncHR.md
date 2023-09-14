#### Sync Heart Rate


**JSON fields received by the app**:

| Field Name        | Data Type | Description                                                  |
| ----------------- | --------- | ------------------------------------------------------------ |
| year              | int       | Data date: year                                              |
| month             | int       | Data date: month                                             |
| day               | int       | Data date: day                                               |
| start_time        | int       | Start time in seconds, offset from 0:00                      |
| data_type         | int       | (reserve) ~~0 for invalid, 1 for single value, 2 for maximum and minimum values~~ |
| silent_hr         | int       | Resting heart rate                                           |
| five_min_max_data | int       | Maximum heart rate in a five-minute interval                 |
| five_min_min_data | int       | Minimum heart rate in a five-minute interval                 |
| five_min_avg_data | int       | Average heart rate in a five-minute interval                 |
| five_min_data     | int []    | All heart rate values in a five-minute interval              |
| hr_data_count     | int       | Number of heart rate data points for high and low heart rates <br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |
| hr_interval       | array     | Five heart rate intervals: warm-up zone, maximum heart rate zone, fat burning zone, aerobic endurance zone, anaerobic endurance zone<br />Array of `threshold` and `minute` |
| items             | array     | Heart rate data points:` offset` and `heart_rateVal`         |
| hr_data           | array     | High and low heart rate data: `hour`, `minute`, `type`, and `heart_rate`<br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |

| Field Name      | Data Type | Description              |
| --------------- | --------- | ------------------------ |
| offset          | int       | Offset in seconds        |
| heart_rateVal   | int       | Heart rate value          |

| Field Name   | Data Type | Description |
| ------------ | --------- | ----------- |
| threshold    | int       | Threshold   |
| minute       | int       | Minute      |

| Field Name | Data Type | Description                                                  |
| ---------- | --------- | ------------------------------------------------------------ |
| hour       | int       | Hour of the high and low heart rate data<br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |
| minute     | int       | Minute of the high and low heart rate data<br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |
| type       | int       | Type of heart rate value<br />0: Heart rate value for low heart rate<br />1: Heart rate value for high heart rate<br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |
| heart_rate | int       | Heart rate value in beats per minute<br />Returns 0 if `v3SupportSyncOverHighLowHeartData` is not enabled. |

`Example:`

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "start_time": 0,
    "data_type": 0,
    "silent_hr": 85,
    "five_min_max_data": 0,
    "five_min_min_data": 0,
    "five_min_avg_data": 0,
    "hr_data_count": 2,
    "five_min_data": [
        85,
        90,
        80,
        83
    ],
    "hr_interval": [
        {
            "threshold": 80,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        },
        {
            "threshold": 85,
            "minute": 5
        }
    ],
    "items": [
        {
            "offset": 80,
            "heart_rateVal": 5
        },
        {
            "offset": 83,
            "heart_rateVal": 5
        }
    ],
    "hr_data": [
        {
            "hour": 11,
            "minute": 25,
            "type": 1,
            "heart_rate": 120
        },
        {
            "hour": 11,
            "minute": 25,
            "type": 0,
            "heart_rate": 70
        }
    ]
}
```
