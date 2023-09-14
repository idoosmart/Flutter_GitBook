### Lastest Getting V3 Sports Data

function table：syncV3ActivityExchangeData 【syncExchangeDataReplyAddRealTimeSpeedPaceV3，setSupportSportPlan，supportSmartCompetitor】


**Flutter Example:**

```dart
/// app get v3 activity data event
exchangeAppGetActivityData(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.func_v3_get_activity_data),

/// app get v3 activity data
libManager.send(evt: CmdEvtType.exchangeAppGetActivityData, json: jsonEncode(json));
```



**JSON Fields Received by App**:

| Field Name                 | Field Type | Field Description                                            |
| -------------------------- | ---------- | ------------------------------------------------------------ |
| version                    | int        | Protocol library version, default 16<br />If `setSupportSportPlan` is enabled, version=32.<br />If `syncExchangeDataReplyAddRealTimeSpeedPaceV3` is enabled, version=48. |
| type                       | int        | Sports type                                                  |
| year                       | int        | Year                                                         |
| month                      | int        | Month                                                        |
| day                        | int        | Day                                                          |
| hour                       | int        | Hour                                                         |
| minute                     | int        | Minute                                                       |
| second                     | int        | Second                                                       |
| hr_data_interval_minute    | int        | Heart rate interval<br />Uint:minutes                    |
| step                       | int        | Number of steps                                              |
| durations                  | int        | Duration<br />Uint:second                             |
| calories                   | int        | Calories<br />Uint:Kcal                                  |
| distance                   | int        | Distance<br />Uint:meter                                     |
| burn_fat_mins              | int        | Duration of fat-burning heart rate<br />Uint:minutes   |
| aerobic_mins               | int        | Duration of aerobic exercise                                  |
| limit_mins                 | int        | Duration of limit exercise                                    |
| warm_up                    | int        | Warm-up exercise (field repeated)                            |
| fat_burning                | int        | Fat-burning exercise (field repeated)                         |
| aerobic_exercise           | Int        | Aerobic exercise (field repeated)                             |
| anaerobic_exercise         | int        | Anaerobic exercise (field repeated)                           |
| extreme_exercise           | int        | Extreme exercise (field repeated)                             |
| warm_up_time               | int        | Accumulated time of warm-up exercise<br />Uint:seconds   |
| fat_burning_time           | int        | Accumulated time of fat-burning exercise<br />Uint:seconds |
| aerobic_exercise_time      | int        | Accumulated time of aerobic exercise<br />Uint:seconds |
| anaerobic_exercise_time    | int        | Accumulated time of anaerobic exercise<br />Uint:seconds |
| extreme_exercise_time      | int        | Accumulated time of extreme exercise<br />Uint:seconds |
| avg_speed                  | int        | Average speed<br />Uint:km/h                            |
| max_speed                  | int        | Maximum speed<br />Uint:km/h                            |
| avg_step_stride            | int        | Average step stride<br />Uint:centimetre                  |
| max_step_stride            | int        | Maximum step stride<br />Uint:centimetre                     |
| km_speed                   | int        | Average pace per kilometer<br />Seconds per kilometer        |
| fast_km_speed              | int        | Fastest pace per kilometer<br />Seconds per kilometer        |
| avg_step_frequency         | int        | Average step frequency<br />Steps per minute                 |
| max_step_frequency         | int        | Maximum step frequency<br />Steps per minute                 |
| avg_hr_value               | int        | Average heart rate<br />Uint:BPM                           |
| max_hr_value               | int        | Maximum heart rate<br />Uint:BPM                            |
| km_speed_count             | int        | Count of pace per kilometer details, maximum 100              |
| steps_frequency_count      | int        | Count of step frequency details                              |
| mi_speed_count             | int        | Count of pace per mile details, maximum 100                   |
| recover_time               | int        | Recovery time, in hours<br />After the app receives this data, it needs to decrement by one every hour |
| vo2max                     | int        | Maximum oxygen consumption, in ml/kg/min                     |
| training_effect            | int        | Training effect, range: 1.0 - 5.0 (transmitted enlarged by 10) |
| grade                      | int        | Oxygen consumption grade<br />1: Low 2: Amateur 3: General 4: Average 5: Good 6: Excellent 7: Professional |
| act_type | int | Plan type:<br />1: 3km running plan<br />2: 5km running plan<br />3: 10km running plan<br />4: Half marathon training (Phase 2)<br />5: Marathon training (Phase 2)<br />64: 6 minutes easy run<br />65: 10 minutes easy run<br />66: 15 minutes easy run<br />67: Beginner walk-run combination<br />68: Intermediate walk-run combination<br />69: Advanced walk-run combination<br />128: Post-run stretch |
| training_offset | int | Training course date offset, starting from zero<br />Effective when version=32, otherwise reported as 0 |
| action_data_count | int | Number of action training<br />Effective when version=32, otherwise reported as 0 |
| in_class_calories | int | Calories burned in class, in kcal<br />Effective when version=32, otherwise reported as 0 |
| completion_rate | int | Action completion rate 0–100<br />Effective when version=32, otherwise reported as 0 |
| hr_completion_rate | int | Heart rate control rate 0–100<br />Effective when version=32, otherwise reported as 0 |
| smart_competitor | int | 0: Invalid 1: Non-intelligent companion running 2: Intelligent companion running<br />Effective when `supportSmartCompetitor` is enabled, otherwise reported as 0 |
| ai_image_id      | int | AI image ID<br />Effective when support_smart_competitor is enabled, otherwise reported as 0 |
| user_image_id | int | User image ID<br />Effective when `supportSmartCompetitor` is enabled, otherwise reported as 0 |
| bg_image_id | int | Background image ID<br />Effective when `supportSmartCompetitor` is enabled, otherwise reported as 0 |
| smart_competitor_pace | int | Intelligent companion running opponent's pace<br />Effective when `supportSmartCompetitor` is enabled, otherwise reported as 0 |
| real_speed_count        | int      | Count of real-time speed<br />Effective when version=48, otherwise reported as 0 |
| pace_speed_count        | int      | Array of real-time pace<br />Effective when version=48, otherwise reported as 0 |
| km_speed_s              | int []    | Seconds per kilometer, pace speed                                          |
| steps_frequency         | int []    | Step frequency in steps per minute                                       |
| items_mi_speed          | int []    | Array of pace speed in seconds per mile               |
| item_real_speed         | int []    | Real-time speed in km/h, with a maximum of 6 hours of data at 5-second intervals. If version=48, the field is valid; otherwise, it is reported as 0 |
| pace_speed_items        | int []    | Array of real-time pace speed in seconds, with a 5-second interval. If version=48, the field is valid; otherwise, it is reported as 0 |
| items | Collection | Details of completed actions including type, heart_contr_value, time, goal_time. If version=32, the field is valid; otherwise, it is reported as 0 |

| Field Name             | Field Type | Field Description                                                     |
| ------------------ | -------- | ------------------------------------------------------------ |
| type               | int      | Type of action: 1=brisk walking, 2=jogging, 3=medium-speed running, 4=sprinting. If version=32, the field is valid; otherwise, it is reported as 0 |
| heart_con_value    | int      | Heart rate control value for each action. If version=32, the field is valid; otherwise, it is reported as 0    |
| time               | int      | Time to complete the action in seconds. If version=32, the field is valid; otherwise, it is reported as 0 |
| goal_timegoal_time | int      | Goal time for the action. If version=32, the field is valid; otherwise, it is reported as 0        |

`Example:`

```json
{
    "version":0,
    "type":0,
    "year":0,
    "month":0,
    "day":0,
    "hour":0,
    "minute":0,
    "second":0,
    "hr_data_interval_minute":0,
    "step":0,
    "durations":0,
    "calories":0,
    "distance":0,
    "burn_fat_mins":0,
    "aerobic_mins":0,
    "limit_mins":0,
    "warm_up":0,
    "fat_burning":0,
    "aerobic_exercise":0,
    "anaerobic_exercise":0,
    "extreme_exercise":0,
    "warm_up_time":0,
    "fat_burning_time":0,
    "aerobic_exercise_time":0,
    "anaerobic_exercise_time":0,
    "extreme_exercise_time":0,
    "avg_speed":0,
    "max_speed":0,
    "avg_step_stride":0,
    "max_step_stride":0,
    "km_speed":0,
    "fast_km_speed":0,
    "avg_step_frequency":0,
    "max_step_frequency":0,
    "avg_hr_value":0,
    "max_hr_value":0,
    "km_speed_count":0,
    "steps_frequency_count":0,
    "mi_speed_count":0,
    "recover_time":0,
    "vo2max":0,
    "training_effect":0,
    "grade":0,
    "act_type":0,
    "training_offset":0,
    "action_data_count":0,
    "in_class_calories":0,
    "completion_rate":0,
    "hr_completion_rate":0,
    "real_speed_count":0,
    "pace_speed_count":0,
    "km_speed_s":[],
    "steps_frequency":[],
    "items_mi_speed":[],
    "item_real_speed":[],
    "pace_speed_items":[],
    "items":[
        {
            "type":0,
            "heart_con_value":0,
            "time":0,
            "goal_timegoal_time":0
        },
        {
            "type":0,
            "heart_con_value":0,
            "time":0,
            "goal_timegoal_time":0
        }
    ]
}
```