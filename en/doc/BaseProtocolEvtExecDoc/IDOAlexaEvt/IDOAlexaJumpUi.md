### APP Jump to UI for ALEXA


Function ID: alexaSetJumpUiV3

**JSON fields sent by the App**:

| Field Name | Field Type | Field Description                                                |
| ---------- | ---------- | ---------------------------------------------------------------- |
| type       | int        | 0: Health data page<br />1: Sleep page<br />2: Heart rate detection<br />3: Stress detection<br />4: Blood oxygen detection<br />5: Open help QR code page<br />6: Music control<br />7: Go to message list<br />8: Find phone<br />9: Exercise record page<br />10: Breathing page<br />11: Settings page<br />12: Flashlight<br />13: View all set alarms<br />14: Open brightness settings page<br />15: Open message details<br />16: Display today's calorie value and unit<br />17: Display distance value+unit generated from running today<br />18: Display value of exercise records today (reserved for exercise records)<br />19: Display corresponding swimming value<br />20: Display corresponding exercise statistics for the day (reserved)<br />21: Display sleep score and duration for the day<br />22: Display running count for the day<br />23: Display swimming count for the day<br />24: Display exercise count for the day<br />25: Skin temperature page<br />26: Noise measurement page<br />27: Open phone page<br />28: Reminder page<br />29: Stopwatch page<br />30: Wrist lifting to wake screen<br />31: Shutdown<br />32: Reboot<br />33: Dial pad<br />34: Favorite contacts<br />35: Call history<br />36: Running course<br />37: Remote camera<br />38: Check body battery level |

`Example:`

```json
{
    "type": 1
}
```

**JSON fields returned by the App**:

| Field Name   | Field Type | Field Description            |
| ------------ | ---------- | ---------------------------- |
| is_success   | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```