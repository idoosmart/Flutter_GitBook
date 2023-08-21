#### Sync Exercise Data


**JSON Fields Received by the App:**

| Field Name        | Field Type | Field Description                        |
| ----------------- | ---------- | --------------------------------------- |
| year              | int        | Data date - Year                         |
| month             | int        | Data date - Month                        |
| day               | int        | Data date - Day                          |
| total_step        | int        | Total steps for the day                  |
| total_cal         | int        | Total calories burned for the day        |
| total_distances   | int        | Total distance covered for the day       |
| total_active_time | int        | Total active time for the day (in minutes) |
| minute_offset     | int        | Start time offset of the data from 00:00 (in minutes) |
| per_minute        | int        | Interval between data points (in minutes) |
| keyword           | int        | Reserved field                           |
| items             | Array      | Exercise details: sport_count, active_time, calories, and distance for each exercise |

| Field Name   | Field Type | Field Description                        |
| ------------ | ---------- | --------------------------------------- |
| sport_count  | int        | Step count                               |
| active_time  | int        | Exercise duration (in minutes)           |
| calories     | int        | Calories burnt                           |
| distance     | int        | Distance covered (in meters)             |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 23,
    "total_step": 20,
    "total_cal": 200,
    "total_distances": 500,
    "total_active_time": 6,
    "minute_offset": 0,
    "per_minute": 15,
    "keyword": 0,
    "items": [
        {
            "sport_count": 2,
            "active_time": 2,
            "calories": 50,
            "distance": 100
        },
        {
            "sport_count": 8,
            "active_time": 2,
            "calories": 50,
            "distance": 200
        },
        {
            "sport_count": 10,
            "active_time": 2,
            "calories": 100,
            "distance": 200
        }
    ]
}
```