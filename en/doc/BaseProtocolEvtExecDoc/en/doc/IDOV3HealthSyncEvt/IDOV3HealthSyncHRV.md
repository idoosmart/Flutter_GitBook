#### Sync HRV Data


**JSON fields received by the App**:

| Field Name | Field Type | Field Description                |
| ---------- | ---------- | ------------------------------- |
| year       | int        | Data date (year)                 |
| month      | int        | Data date (month)                |
| day        | int        | Data date (day)                  |
| start_time | int        | Start time in seconds from 00:00 |
| items      | array      | Array of HRV data details, with min_offset and hrv_value |

| Field Name  | Field Type | Field Description    |
| ----------- | ---------- | -------------------  |
| min_offset  | int        | Default offset in minutes |
| hrv_value   | int        | HRV data             |

`Example:`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "start_time":0,
    "items":[
        {
            "min_offset":5,
            "hrv_value":0
        },
        {
            "min_offset":5,
            "hrv_value":0
        }
    ]
}
```