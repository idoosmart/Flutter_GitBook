#### Get Total Package Count for GPS and Multiple Sports Sync


**JSON Fields Sent by the App:**

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
|            |            |                   |

**JSON Fields Received by the App:**

| Field Name        | Field Type | Field Description            |
| ----------------- | ---------- | ---------------------------- |
| activity_count    | int        | Number of activity (multiple sports) data |
| activity_packet   | int        | Total number of packets for activity data |
| gps_count         | int        | Number of GPS data           |
| gps_packet        | int        | Total number of packets for GPS data |

**Example:**

```c
{
    "activity_count": 2,
    "activity_packet": 1,
    "gps_count": 2,
    "gps_packet": 1
}
```