### Get find phone switch (GET:0x02/0x26)

Function table: `supportGetFindPhoneSwitch` (`support_get_find_phone_switch`)

**Flutter example:**

```dart
libManager.send(evt: CmdEvtType.getFindPhoneSwitch, json: jsonEncode({}));
```

**JSON fields in the app callback:**

| Field | Type | Description |
| ----- | ---- | ----------- |
| onOff | bool | On: `true` (`0xAA`); off: `false` (`0x55`) |

Example:

```json
{"onOff": true}
```

**Notes:**

- Check `libManager.funTable.supportGetFindPhoneSwitch` before sending.
