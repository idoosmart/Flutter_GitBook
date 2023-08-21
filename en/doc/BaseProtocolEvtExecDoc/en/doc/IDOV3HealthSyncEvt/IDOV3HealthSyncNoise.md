#### Sync Environment Volume (Noise)


**JSON fields received by the App**:

| Field Name     | Field Type | Field Description             |
| -------------- | ---------- | ---------------------------- |
| year           | int        | Data date (year)              |
| month          | int        | Data date (month)             |
| day            | int        | Data date (day)               |
| hour           | int        | Data date (hour)              |
| minute         | int        | Data date (minute)            |
| second         | int        | Data date (second)            |
| version        | int        | Protocol version (0)          |
| start_time     | int        | Sync start time in seconds    |
| interval_mode  | int        | Interval between two data points in seconds |
| avg_noise      | int        | Average noise value            |
| max_noise      | int        | Maximum noise value            |
| min_noise      | int        | Minimum noise value            |
| noise_count    | int        | Number of noise detail items   |
| items          | array      | Array of noise detail items with offset and value |

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| offset     | int        | Offset of the data |
| value      | int        | Noise value        |

`Example:`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "hour":11,
    "minute":58,
    "second":30,
    "version":0,
    "start_time":0,
    "interval_mode":30,
    "avg_noise":50,
    "max_noise":60,
    "min_noise":40,
    "noise_count":2,
    "items":[
        {
            "offset":30,
            "value":50
        },
        {
            "offset":30,
            "value":50
        }
    ]
}
```