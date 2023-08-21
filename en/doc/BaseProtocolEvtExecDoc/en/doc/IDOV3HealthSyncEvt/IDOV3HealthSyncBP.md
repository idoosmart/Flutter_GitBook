#### Sync Blood Pressure Data


**JSON fields received by the app**:

| Field Name     | Data Type | Description                           |
| -------------- | --------- | ------------------------------------- |
| year           | int       | Data date: year                       |
| month          | int       | Data date: month                      |
| day            | int       | Data date: day                        |
| start_time     | int       | Start time in seconds from 0:00        |
| sleep_avg_bp   | int       | Average blood pressure during sleep    |
| max_bp         | int       | Maximum blood pressure                 |
| item_count     | int       | Number of blood pressure details       |
| items          | array     | Blood pressure details: offset, sys_blood, dias_blood |

| Field Name     | Data Type | Description                                                                         |
| -------------- | --------- | ----------------------------------------------------------------------------------- |
| offset         | int       | Data offset in minutes (blood pressure data is offset by minutes)                   |
| sys_blood      | int       | Systolic blood pressure                                                             |
| dias_blood     | int       | Diastolic blood pressure                                                            |

`Example:`

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "start_time": 0,
    "sleep_avg_bp": 0,
    "max_bp": 0,
    "item_count": 3,
    "items": [
        {
            "offset": 5,
            "sys_blood": 120,
            "dias_blood": 70
        },
        {
            "offset": 5,
            "sys_blood": 120,
            "dias_blood": 70
        },
        {
            "offset": 5,
            "sys_blood": 120,
            "dias_blood": 70
        }
    ]
}
```
