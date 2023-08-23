### Control command for ALEXA sent by the app

Menu: alexaSetEasyOperateV3

**JSON fields sent by the app**:

| Field Name     | Field Type | Field Description                                                                                                                        |
| -------------- | ---------- | --------------------------------------------------------------------------------------------------------------------------------------- |
| ui_type        | int        | 1: Brightness control<br/>2: Do Not Disturb control<br/>3: Raise-to-Wake control                                                        |
| operation_type | int        | for ui_type 1 (Brightness control):<br/>operation_type<br/>0: Increase brightness on the brightness control screen<br/>1: Decrease brightness on the brightness control screen<br/>2: Adjust brightness to maximum<br/>3: Adjust brightness to minimum<br/>4: Set specific brightness level<br/>6: Increase brightness by 10% on the brightness control screen<br/>7: Decrease brightness by 10% on the brightness control screen<br/>8: Set specific brightness level (percentage)<br/>for ui_type 2 (Do Not Disturb control):<br/>0: Enable Do Not Disturb mode<br/>1: Disable Do Not Disturb mode<br/>for ui_type 3 (Raise-to-Wake control):<br/>0: Enable Raise-to-Wake feature<br/>1: Disable Raise-to-Wake feature |
| cmd            | int        | for ui_type 1 and operation_type 4 (brightness control):<br/>This field indicates the brightness level: 1-5 or 1-3, based on the functionality whether it has 3 levels or 5 levels<br/>for ui_type 1 and operation_type 8 (brightness control):<br/>This field indicates the brightness level: 0x01 = 1% brightness, 0x64 = 100% brightness, and so on, each increment represents an increase of 1% brightness, cmd should not exceed 0x64, with a total of 100 levels of brightness |

`Example:`

```json
{
    "ui_type": 3,
    "operation_type": 0,
    "cmd": 0
}
```

**JSON fields returned by the app**:

| Field Name   | Field Type | Field Description |
| ------------ | ---------- | ----------------- |
| is_success   | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```
