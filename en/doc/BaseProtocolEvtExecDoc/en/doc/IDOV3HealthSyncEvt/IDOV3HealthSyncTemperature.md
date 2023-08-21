#### Synchronized Temperature

**JSON fields received by the App**:

| Field Name          | Field Type | Field Description                            |
| ------------------- | ---------- | -------------------------------------------- |
| year                | int        | Data date: year                              |
| month               | int        | Data date: month                             |
| day                 | int        | Data date: day                               |
| hour                | int        | Data date: hour                              |
| minute              | int        | Data date: minute                            |
| start_time          | int        | Start time of synchronization in seconds      |
| interval_mode       | int        | Interval mode: 0 for minutes, 1 for seconds  |
| avg_temperature     | int        | Average temperature                          |
| max_temperature     | int        | Maximum temperature                          |
| min_temperature     | int        | Minimum temperature                          |
| temperature_count   | int        | Number of temperature details                 |
| items               | array      | Temperature details, containing offset and value |

| Field Name | Field Type | Field Description  |
| ---------- | ---------- | ----------------- |
| offset     | int        | Data offset       |
| value      | int        | Temperature value |

`Example:`

```json
{
    "avg_temperature": 0,
    "day": 0,
    "hour": 0,
    "interval_mode": 0,
    "items": null,
    "max_temperature": 0,
    "min_temperature": 0,
    "minute": 0,
    "month": 0,
    "start_time": 0,
    "temperature_count": 0,
    "year": 0
}
```

