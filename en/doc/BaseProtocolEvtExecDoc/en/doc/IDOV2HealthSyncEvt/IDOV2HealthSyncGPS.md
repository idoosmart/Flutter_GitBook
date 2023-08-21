#### Sync GPS Data


**JSON Fields Sent by the App:**

| Field Name      | Field Type | Field Description |
| --------------- | ---------- | ----------------- |
|                 |            |                   |

**JSON Fields Received by the App:**

| Field Name       | Field Type | Field Description |
| ---------------- | ---------- | ----------------- |
| year             | int        | Year              |
| month            | int        | Month             |
| day              | int        | Day               |
| hour             | int        | Hour              |
| minute           | int        | Minute            |
| second           | int        | Second            |
| data_interval    | int        | Data interval in seconds |
| items            | char []    | GPS coordinate string |

**Example:**

```c
{
    "year": 2022,
    "month": 12,
    "day": 26,
    "hour": 10,
    "minute": 22,
    "second": 36,
    "data_interval": 5,
    "items": ""
}
```