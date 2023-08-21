#### Sync Exercise

**JSON fields received by the App**:

| Field Name                    | Field Type | Field Description                                                                                                                        |
| ---------------------------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| version                      | int        | Protocol version<br />0: No wear flag data<br />16: Wear flag data is available, firmware configuration requires support_wear_flag_33_04_08 |
| year                         | int        | Data date (year)                                                                                                                        |
| month                        | int        | Data date (month)                                                                                                                       |
| day                          | int        | Data date (day)                                                                                                                         |
| start_time                   | int        | Start time in minutes, offset from 00:00                                                                                                 |
| per_minute                   | int        | Interval in minutes for each data entry (default: 15 minutes)<br />Customization: Added support for interval duration of 1 minute<br />If the interval is 1 minute, the app needs to check support_per_minute_one in order to determine if the firmware supports one-minute sync type |
| total_step                   | int        | Total number of steps                                                                                                                    |
| total_rest_activity_calories | int        | Total activity and rest calories                                                                                                         |
| total_distances              | int        | Total distance (miles) = Firmware distance (in meters) multiplied by 0.00062                                                             |
| total_active_time            | int        | Total active time in minutes                                                                                                             |
| total_activity_calories      | int        | Total activity calories                                                                                                                  |
| walk_goal_time | int | Actual walking duration configured in firmware (in hours) |
| item_count                   | int        | Number of exercise data entries                                                                                                          |
| wear_flag_array | int []     | Array of 24 wear minutes for each hour of the day<br />Returns 0 when V3_support_sync_over_high_low_heart_data is not enabled in the firmware |
| items                        | array      | Exercise data entries, consisting of mode, step_count, active_time, activity_calories, distance, and rest_activity_calories              |

| Field Name                 | Field Type | Field Description                                                            |
| -------------------------- | ---------- | --------------------------------------------------------------------------- |
| mode                       | int        | Mode: 00 for quiet, 01 for light, 10 for moderate, 11 for intense            |
| step_count                 | int        | Number of steps                                                              |
| active_time                | int        | Active duration in minutes, with a maximum determined by the per_minute parameter (currently set at 15 minutes) |
| activity_calories          | int        | Activity calories                                                            |
| distance                   | int        | Distance in meters                                                           |
| rest_activity_calories     | int        | Activity and rest calories                                                    |

`Example:`

```c
{
    "day" : 26,
      "item_count" : 47,
      "items" :
      [
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        },
        {
          "active_time" : 0,
          "activity_calories" : 0,
          "distance" : 0,
          "mode" : 0,
          "rest_activity_calories" : 0,
          "step_count" : 0
        }
      ],
      "month" : 12,
      "per_minute" : 15,
      "start_time" : 0,
      "total_active_time" : 0,
      "total_activity_calories" : 0,
      "total_distances" : 0,
      "total_rest_activity_calories" : 0,
      "total_step" : 0,
      "version" : 0,
      "walk_goal_time" : 0,
      "wear_flag_array" :
      [
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0,
        0
      ],
      "year" : 2022
}
```
