#### Sync Respiratory Rate Data


**JSON fields received by the App**:

| Field Name    | Field Type | Field Description                    |
| ------------- | ---------- | -----------------------------------  |
| year          | int        | Data date (year)                     |
| month         | int        | Data date (month)                    |
| day           | int        | Data date (day)                      |
| item_count    | int        | Number of respiratory rate details   |
| items         | array      | Array of respiratory rate details with start time and respid |

| Field Name    | Field Type | Field Description                  |
| ------------- | ---------- | ---------------------------------  |
| start_time    | int        | Start time in seconds from 00:00   |
| respid        | int        | Respiratory rate value              |

`Example:`

```c
{
    "year":2022,
    "month":12,
    "day":26,
    "item_count":3,
    "items":[
        {
            "start_time":0,
            "respid":80
        },
        {
            "start_time":100,
            "respid":80
        },
        {
            "start_time":100,
            "respid":80
        }
    ]
}
```