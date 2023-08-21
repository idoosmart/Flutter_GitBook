#### Synchronized Swimming

**JSON fields received by the App**:

| Field Name           | Field Type | Field Description                                            |
| -------------------- | ---------- | ------------------------------------------------------------ |
| year                 | int        | Data date: year                                              |
| month                | int        | Data date: month                                             |
| day                  | int        | Data date: day                                               |
| hour                 | int        | Data date: hour                                              |
| minute               | int        | Data date: minute                                            |
| second               | int        | Data date: second                                            |
| version              | int        | Protocol version number                                      |
| type                 | int        | Type: 0 invalid, 1 indoor swimming, 2 open water swimming     |
| calories             | int        | Calories burned                                              |
| distance             | int        | Distance in meters                                           |
| confirm_distance     | int        | User-confirmed distance                                      |
| duration             | int        | Duration in seconds                                          |
| trips                | int        | Number of swimming laps                                      |
| average_swolf        | int        | Average swolf                                                |
| total_strokes_number | int        | Total number of strokes                                      |
| swimming_posture     | int        | Main swimming posture: 0: mixed style, 1: freestyle, 2: breaststroke, 4: other  |
| pool_distance        | int        | Pool distance in cm                                          |
| avg_speed            | int        | Average speed<br />Valid for version=1, otherwise the field is 0 |
| avg_frequency        | int        | Average stroke frequency<br />Valid for version=1, otherwise the field is 0 |
| items                | array      | Swimming data details, containing swolf, strokesNumber, duration, swimmingPosture, distance, frequency, speed, stop_time, difference_time |

| Field Name          | Field Type | Field Description                                      |
| ------------------- | ---------- | ----------------------------------------------------- |
| swolf               | int        | Stroke efficiency                                      |
| strokes_number      | int        | Swimming posture                                      |
| duration            | int        | Stroke count                                          |
| swimming_posture    | int        | Time in seconds                                       |
| distance            | int        | Distance                                              |
| frequency           | int        | Stroke frequency<br />Valid for version=1, otherwise the field is 0 |
| speed               | int        | Pace in km/h<br />Valid for version=1, otherwise the field is 0 |
| stop_time           | int        | End time<br />Valid for version=1, otherwise the field is 0 |
| difference_time     | int        | Rest time between two laps<br />Valid for version=1, otherwise the field is 0 |

`Example:`

```json
{

}
```
The above Chinese text has been translated into English. Other structures should not be changed.