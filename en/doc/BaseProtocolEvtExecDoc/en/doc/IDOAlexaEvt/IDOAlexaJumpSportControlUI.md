### ALEXA Jump to Sports Page


Function ID: alexaSetJumpSportUiV3

**JSON fields received by the App**:

| Field Name     | Field Type | Field Description                                                 |
| -------------- | ---------- | ----------------------------------------------------------------- |
| sports_type    | int        | 20 types of sports                                                |
| v2_sport_type  | int        | 100 types of sports<br />When using this field, set sports_type to 0<br />Requires firmware support for V3_set_100_sport_sort |

`Example:`

```json
{
    "sports_type": 0,
    "v2_sport_type": 20
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