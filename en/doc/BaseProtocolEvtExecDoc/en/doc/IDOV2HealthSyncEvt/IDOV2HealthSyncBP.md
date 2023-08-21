#### Synchronize Blood Pressure Data


**JSON Fields Sent by the App:**

| Field Name        | Field Type | Field Description         |
| ----------------- | ---------- | ------------------------- |
| year              | int        | Year                      |
| month             | int        | Month                     |
| day               | int        | Day                       |
| sleep_avg_bp      | int        | Average sleep blood pressure |
| max_bp            | int        | Maximum blood pressure    |
| minute_offset     | int        | Minute offset from midnight |
| items             | array      | Blood pressure details    |

**JSON Fields Received by the App:**

| Field Name     | Field Type | Field Description                                |
| -------------- | ---------- | ------------------------------------------------ |
| offset         | int        | Offset of the data in minutes from midnight     |
| dias_blood     | int        | Diastolic blood pressure (low pressure)          |
| sys_blood      | int        | Systolic blood pressure (high pressure)           |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "sleep_avg_bp": 86,
    "max_bp": 90,
    "minute_offset": 15,
    "items": [
        {
            "offset": 5,
            "dias_blood": 70,
            "sys_blood": 90
        },
        {
            "offset": 5,
            "dias_blood": 69,
            "sys_blood": 87
        },
        {
            "offset": 5,
            "dias_blood": 76,
            "sys_blood": 88
        }
    ]
}
```