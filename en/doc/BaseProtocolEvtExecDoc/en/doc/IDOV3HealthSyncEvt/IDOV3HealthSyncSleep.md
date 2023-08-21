#### Sleep Synchronization

**JSON fields received by the app**:

| Field Name                  | Data Type | Field Description                                            |
| --------------------------- | --------- | ------------------------------------------------------------ |
| data_type                   | int       | The return value defined by the app. bit0: 1 for normal sleep, bit1: 2 for nap, bit2 (4) for unsupported scientific sleep. Return values defined by the algorithm: 1: scientific sleep (with REM and breath score); 2: nap; 4: ordinary sleep |
| fall_asleep_year            | int       | Year of falling asleep                                       |
| fall_asleep_month           | int       | Month of falling asleep                                      |
| fall_asleep_day             | int       | Day of falling asleep                                        |
| fall_asleep_hour            | int       | Hour of falling asleep                                       |
| fall_asleep_minte           | int       | Minute of falling asleep                                     |
| get_up_year                 | int       | Year of getting up                                           |
| get_up_month                | int       | Month of getting up                                          |
| get_up_day                  | int       | Day of getting up                                            |
| get_up_hour                 | int       | Hour of getting up                                           |
| get_up_minte                | int       | Minute of getting up                                         |
| total_sleep_time_mins       | int       | Total sleep duration in minutes                              |
| wake_mins                   | int       | Total time awake in minutes                                  |
| light_mins                  | int       | Total duration of light sleep in minutes                     |
| rem_mins                    | int       | Total duration of REM sleep in minutes                       |
| deep_mins                   | int       | Total duration of deep sleep in minutes                      |
| wake_count                  | int       | Number of times awake during sleep                            |
| light_count                 | int       | Number of times in light sleep during sleep                   |
| rem_count                   | int       | Number of times in REM sleep during sleep                     |
| deep_count                  | int       | Number of times in deep sleep during sleep                    |
| awrr_status                 | int       | Breathing status during sleep                                |
| sleep_score                 | int       | Sleep score                                                  |
| breath_quality              | int       | Breath quality (0-100) without a unit                        |
| sleep_avg_hr_value          | int       | Average heart rate during sleep stages                        |
| sleep_avg_spo2_value        | int       | Average blood oxygen level during sleep stages                |
| sleep_avg_respir_rate_value | int       | Average respiratory rate during sleep stages                 |
| item_count                  | int       | Number of sleep details                                      |
| items                       | array     | Sleep details, a collection of stage and duration            |

| Field Name  | Data Type | Field Description                                       |
| ----------- | --------- | ------------------------------------------------------ |
| stage       | int       | Stage: 1: Awake, 2: Light sleep, 3: Deep sleep, 4: REM  |
| duration    | int       | Duration in seconds                                    |

`Example:`

```c
{
    "awrr_status" : 0,
    "breath_quality" : 0,
    "data_type" : 1,
    "deep_count" : 0,
    "deep_mins" : 0,
    "fall_asleep_day" : 0,
    "fall_asleep_hour" : 0,
    "fall_asleep_minte" : 0,
    "fall_asleep_month" : 0,
    "fall_asleep_year" : 0,
    "get_up_day" : 0,
    "get_up_hour" : 0,
    "get_up_minte" : 0,
    "get_up_month" : 0,
    "get_up_year" : 0,
    "item_count" : 0,
    "items" : null,
    "light_count" : 0,
    "light_mins" : 0,
    "rem_count" : 0,
    "rem_mins" : 0,
    "sleep_score" : 0,
    "total_sleep_time_mins" : 0,
    "wake_count" : 0,
    "wake_mins" : 0
}
```
