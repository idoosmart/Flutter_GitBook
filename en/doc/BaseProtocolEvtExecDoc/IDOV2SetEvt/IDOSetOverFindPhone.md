### Stop Find Phone

Menu: setOverFindPhone

**JSON Fields Sent by the App**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| states     | int        | 1: Stop finding   |

`Example:`

```json
{
  "states": 1
}
```



**JSON Fields Received by the App**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| status     | int        | 0 for success<br />1 for failure |

`Example:`

```json
{
  "status": 0
}
```