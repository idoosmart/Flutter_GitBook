### Timer Function in the App

Menu: getVoiceTransmission

**JSON fields sent by the app**:

| Field Name         | Field Type | Field Description                                    |
| ------------------ | ---------- | --------------------------------------------------- |
| delay_time         | int        | Set the corresponding stopwatch data                 |
| index              | int        | Starting from 0                                      |
| operate_timer_flag | int        | Operation flag: <br />0: Add <br />1: Delete timer (determined by index)<br />255: Cancel all timers |

`Example:`

```json
{
    "delay_time": 10,
    "index": 0,
    "operate_timer_flag": 0
}
```

**JSON fields returned by the app**:

| Field Name  | Field Type | Field Description |
| ----------- | ---------- | ----------------- |
| is_success  | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```
