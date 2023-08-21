#### Sync Stress


**JSON fields received by the App**:

| Field Name  | Field Type | Field Description                   |
| ----------- | ---------- | ----------------------------------  |
| year        | int        | Data date (year)                     |
| month       | int        | Data date (month)                    |
| day         | int        | Data date (day)                      |
| start_time  | int        | Start time in seconds from 00:00     |
| data_type   | int        | 0: Invalid, 1: Single value, 2: Maximum and minimum values |
| items       | array      | Array of stress data details with offset and value |

| Field Name | Field Type | Field Description      |
| ---------- | ---------- | ---------------------- |
| offset     | int        | Offset in minutes      |
| value      | int        | Stress value            |

`Example:`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "data_type":1,
    "items":[
        {
            "offset":30,
            "value":30
        },
        {
            "offset":30,
            "value":30
        }
    ]
}
```