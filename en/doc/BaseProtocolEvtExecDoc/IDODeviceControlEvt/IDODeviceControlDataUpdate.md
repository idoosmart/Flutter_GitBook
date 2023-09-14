### Device Notification APP Data Update


**JSON Fields Received by the App**:

| Field Name   | Field Type | Field Description                                            |
| ------------ | ---------- | ------------------------------------------------------------ |
| data_type    | int        | [Jump to Details](#datatype)                                |
| notify_type  | int        | [Jump to Details](#notifytype)                              |
| msg_ID       | int        | Reserved                                                     |
| msg_notice   | int        | Reserved                                                     |
| error_index  | int        | [Jump to Details](#errorindex)<br />Firmware error code return<br />Non-zero indicates an error, refer to the firmware error code<br />If the app receives a non-zero error, send the command to collect flash data of device 0x21 11 |

`Example:`

```c
{
    "data_type":1,
    "notify_type":0,
    "msg_ID":0,
    "msg_notice":0,
    "error_index":0
}
```



<span id=datatype>**`data_type`**</span>

| Decimal Value | Description                                                  |      |
| ------------- | ------------------------------------------------------------ | ---- |
| 0             | Invalid                                                      |      |
| 1             | The bracelet has been unbound                                |      |
| 2             | Heart rate mode has changed                                  |      |
| 3             | Blood oxygen data has changed                                |      |
| 4             | Stress data has changed                                      |      |
| 5             | Exited Alexa recognition process                             |      |
| 6             | Firmware initiates factory reset, notifying the app to display an alert box |      |
| 7             | App needs to enter the camera interface (TIT01 customization) |      |
| 8             | SOS event notification (205 Turkey customization)             |      |
| 9             | Firmware has modified the alarm clock set by Alexa, and needs to send the corresponding notification bit to the app. After receiving the notification, the app sends a command to obtain the V3 alarm clock |      |
| 10            | Firmware has deleted a schedule reminder, and the app needs to update the corresponding list data |      |
| 11            | Firmware has modified the sub-style of the corresponding dial, notifying the app to obtain (command_id is 0x33, key is 0x5000) |      |
| 12            | Firmware notifies iOS to update notification icon and name   |      |
| 13            | Firmware notifies the app that the icon has been updated, notifying the app to obtain the updated icon status |      |
| 14            | Firmware requests to reset the weather, and the app, upon receiving the request, sends weather data |      |
| 15            | Every time the step count increases by 2000 steps, the device requests the app to synchronize data. The app calls the synchronization interface |      |
| 16            | When sleep is detected to be finished, the device requests the app to synchronize sleep data. The app calls the synchronization interface to synchronize |      |
| 17            | Firmware has modified the three-ring data, notifying the app to update the three-ring data |      |
| 18            | Firmware sends a reminder when the device is fully charged, and the app, upon receiving it, displays a notification that the device is fully charged |      |
| 19            | After finishing a workout, manually measuring heart rate, manually measuring blood oxygen, manually measuring stress, the device automatically requests synchronization. It first checks the connection status. If not connected, it does not perform synchronization this time. After meeting the conditions for the next automatic synchronization, it checks again and initiates a synchronization request |      |
| 20            | Firmware has modified the notification status type of heart rate, stress, blood oxygen, physiological cycle, health guidance, and reminder items. Notifies the app to update the notification status type of heart rate, stress, blood oxygen, physiological cycle, health guidance, and reminder items |      |
| 21            | Firmware has completed the calculation of stress value, notifying the app to obtain the stress value |      |
| 22            | Firmware notifies the app that the stress calibration has failed (firmware exits the measurement interface/detection fails/detection timeout/not worn) |      |
| 23            | Reserved                                                     |      |
| 24            | Firmware notifies the app that the Bluetooth connection is established |      |
| 25            | Firmware notifies the app that the Bluetooth connection is disconnected |      |
| 26            | Firmware notifies the start of a Bluetooth call                |      |
| 27            | Firmware notifies the end of a Bluetooth call                  |      |
| 28            | New version firmware sends a notification command every 4 minutes and 30 seconds to fix the issue of iOS showing offline |      |
| 29            | Notify the app that the workout has started (used to intercept dial transmission, same as 26) |      |
| 30            | Notify the app that the workout has ended (used to intercept dial transmission, same as 27) |      |
| 31            | Firmware sends a notification to the app when it restarts (the app needs to obtain firmware version information upon receiving the notification) |      |
| 32            | When the device is idle (not using Alexa), it needs to report a notification to the app (interval is 1 hour) |      |
| 33            | Firmware notifies the app to continue transmitting dial files after completing space organization |      |
| 34            | Firmware notifies the app to end the find bracelet command (corresponding to 6.3 find bracelet) |      |
| 35            | Firmware notifies the app that it has entered power-saving mode |      |
| 36            | Firmware notifies the app that it has exited power-saving mode  |      |
| ~~37~~        | ~~Firmware notifies the app to send the GPS hot start parameter settings (obsolete)~~ |      |
| 38            | Firmware notifies that the transmission of raw data is complete, and notifies the app to obtain feature vector information |      |
| 39            | Firmware notifies the app that the blood pressure calibration has failed (firmware exits the measurement interface/detection fails/detection timeout/not worn) |      |
| 40            | Firmware notifies that the transmission of raw data is complete, but there is no feature vector information, and notifies the app that data collection is complete |      |
| 41            | V3 health data synchronization single item data completion notification (used internally by Android) |      |
| 42            | Firmware notifies the app that it has completed the organization of GPS data space, and requests the app to send GPS files |      |
| 43            | Firmware update of EPO.dat file failed, notifies the app to re-send the file |      |
| 44            | Firmware update of EPO.dat file successful                      |      |
| 45            | Firmware upgrade of GPS failed, notifies the app to retransmit  |      |
| 46            | Firmware upgrade of GPS successful                              |      |
| 47            | When starting a workout, if the firmware detects abnormal GPS, it notifies the app |      |
| 48            | Firmware updates information of Runde Device, notifies the app to obtain it |      |
| 49            | Firmware notifies the user to cancel the BLE connection with the watch, and the app displays a popup window to handle it |      |
| 50            | Firmware notifies the app that the BT pairing is complete      |      |
| 51            | Firmware sets the workout order, notifies the app to obtain workout order information |      |
| 52            | Firmware has changed the all-day step goal parameter, notifies the app to obtain the all-day step goal (0208) |      |
| 53            | Firmware notifies the app that it has entered the blood pressure calibration interface |      |
| 54            | Firmware updates the automatic recognition switch status, notifies the app to obtain the status of the workout automatic recognition switch (02EA) | |



<span id=notifytype>**`notify_type (bitwise access)`**</span>

| Value | Description                                               | Bit  |
| ----- | --------------------------------------------------------- | ---- |
| 1     | Alarm modified                                           | bit0 |
| 2     | Firmware overheating warning                              | bit1 |
| 4     | Brightness parameter modified (02 b0)                     | bit2 |
| 8     | Lift wrist parameter modified (02 b1)                     | bit3 |
| 16    | Do Not Disturb mode obtained (02 30)                      | bit4 |
| 32    | Phone volume issued (03 0xE3) (deleted), app volume modified, directly issued | bit5 |

Note: Heart rate mode reuses the heart rate mode modification of V3, when data_type = 2, the app initiates a heart rate command.



<span id=errorindex>**`error_index`**</span>

| Value | Error Type    | Remark                  |
| ----- | ------------- | ----------------------- |
| 0     | No error      |                         |
| 1     | ACC           | Firmware errors 1~100   |
| 2     | PPG           |                         |
| 3     | TP            |                         |
| 4     | FLASH         |                         |
| 5     | Overheating   | (PPG)                   |
| 6     | Pressure      |                         |
| 7     | GPS           |                         |
| 8     | Magnetism     |                         |
|       |               |                         |
| 100   | Watchdog reset| Reset log codes 100~200 |
| 101   | Power-on reset|                         |
| 102   | Software reset|                         |
| 103   | OTA reset     |                         |
| 104   | User reset    |                         |
| 105   | Low power shutdown reset |                   |
