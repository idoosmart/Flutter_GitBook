#### Blood Oxygen Synchronization


**JSON fields received by the app**:

| Field Name | Data Type | Field Description                                            |
| ---------- | --------- | ------------------------------------------------------------ |
| year       | int       | Data date: year                                              |
| month      | int       | Data date: month                                             |
| day        | int       | Data date: day                                               |
| start_time | int       | Start time in seconds, offset from 0:00                       |
| data_type  | int       | 0: Invalid, 1: Single value, 2: Maximum and minimum value    |
| items      | array     | Collection of offset and value                               |

| Field Name | Data Type | Field Description                                            |
| ---------- | --------- | ------------------------------------------------------------ |
| offset     | int       | Default offset in seconds                                    |
| value      | int       | Blood oxygen average value                                   |

`Example:`

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "start_time": 0,
    "data_type": 1,
    "items": [
        {
            "offset": 30,
            "value": 30
        },
        {
            "offset": 30,
            "value": 30
        }
    ]
}
```