### ~~Device Requests Version Check~~

**JSON fields received by the App**:

| Field Name | Type | Description |
| ---------- | ---- | ----------- |
|            |      |             |

**JSON fields sent by the App**:

| Field Name | Type | Description                                                          |
| ---------- | ---- | -------------------------------------------------------------------- |
| flag       | int  | 0: Already up to date, 1: New version available, 2: Network error, 3: Other error |
| version    | int  | Protocol version                                                     |

`Example`:

```json
{
    "flag": 0,
    "version": 0
}
```
