### App Set ALEXA Switch Command

Menu: alexaSetSetOnOffTypeV3

**JSON fields sent by the app**:

| Field Name | Field Type | Field Description                                            |
| ---------- | ---------- | ------------------------------------------------------------ |
| type       | int        | Type<br />0: sport/exercise (Jump to sports list)<br />1: Outdoor Run<br />2: Indoor run<br />3: Outdoor walk<br />4: Indoor walk<br />5: Hiking<br />6: Outdoor cycle<br />7: Indoor cycle<br />8: Cricket<br />9: Pool Swim<br />10: Open water swim<br />11: Yoga<br />12: Rower<br />13: Elliptical<br />14: Workout<br />15: Sleep/Slept<br />16: Stress/Pressure<br />17: Help (Open help QR code page)<br />18: Find phone<br />19: Breath training/Relax<br />20: Settings/Options<br />21: Flashlight<br />22: Display setting/brightness<br />23: Message/Text notifications<br />24: Skin temperature<br />25: Noise measurement<br />26: Phone<br />27: Event reminder<br />28: Stopwatch<br />29: Running course<br />30: Body power |
| on_off     | int        | On/Off<br />170: On<br />85: Off                             |

`Example:`

```json
{
    "type": 0,
    "on_off": 170
}
```

**JSON fields returned by the app**:

| Field Name | Field Type | Field Description |
| ---------- | ---------- | ----------------- |
| is_success | int        | 1 for success, 0 for failure |

`Example:`

```json
{
    "is_success": 1
}
```
