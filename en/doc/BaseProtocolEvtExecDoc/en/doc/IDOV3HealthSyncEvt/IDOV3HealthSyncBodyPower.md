#### Sync Body Battery Data


**JSON fields received by the app**:

| Field Name  | Data Type | Description                              |
| ----------- | --------- | ---------------------------------------- |
| year        | int       | Data date: year                          |
| month       | int       | Data date: month                         |
| day         | int       | Data date: day                           |
| start_time  | int       | Start time in seconds from 0:00           |
| data_type   | int       | Reserved                                 |
| items       | array     | Body battery details: offset, type, value, diff_value |

| Field Name  | Data Type | Description                                                                   |
| ----------- | --------- | ----------------------------------------------------------------------------- |
| offset      | int       | Default offset in seconds                                                    |
| type        | int       | Label type: <br />0: Not worn 1: Exercise (during workout mode) 2: Relax 3: Stress 4: Activity 5: Exercise (during daily use) |
| value       | int       | Actual value, with decimals. The firmware should multiply the actual value by 100. |
| diff_value  | int       | Difference relative to the previous value. Zero is the baseline. Positive values indicate recovery, negative values indicate consumption. |

`Example:`

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "start_time": 0,
    "data_type": 0,
    "items": [
        {
            "offset": 5,
            "type": 0,
            "value": 80,
            "diff_value": 0
        },
        {
            "offset": 5,
            "type": 0,
            "value": 81,
            "diff_value": 1
        },
        {
            "offset": 5,
            "type": 0,
            "value": 79,
            "diff_value": -2
        }
    ]
}
```
