### Get Watch ID

Menu: getWatchID

**Flutter Example:**

```dart
/// Get watch ID event number
getWatchDialId(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_watch_id),

/// Get watch ID
libManager.send(evt: CmdEvtType.getWatchDialId, json: jsonEncode(json));
```

**JSON Fields Received by the App:**

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| watch_id   | int        | Watch ID          |

**Example:**

```c
{
  "watch_id": 1
}
```