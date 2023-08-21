# {IDO Device Notification/Control Event Description}

## 1. Overview

Provides the capability to listen for notification events, control events, quick messages, and firmware error codes sent from the wristband/watch device to the app.

## 2. Interface Capabilities

### 1. Data Type Notification Event:

#### 1.1 Summary:

Description of data type notification events.

#### 1.2 API ID:

````dart
final int? dataType;
````

#### 1.3 API Parameter Description:

| Decimal Value | Description                                                |      |
| ------------- | ---------------------------------------------------------- | ---- |
| 0             | Invalid                                                    |      |
| 1             | Wristband has been unbound                                 |      |
| 2             | Heart rate mode changed                                    |      |
| 3             | Blood oxygen data generated and changed                    |      |
| 4             | Stress data generated and changed                          |      |
| 5             | Alexa recognition process exited                           |      |
| 6             | Firmware initiated factory reset, notifying app with a popup |      |
| 7             | App needs to enter the camera interface (TIT01 customized)  |      |
| 8             | SOS event notification (205 Turkey customized)              |      |
| 9             | Firmware has modified the alarm set by Alexa, need to send the corresponding notification bit to the app, and app sends the command to get V3 alarm      |      |
| 10             | Firmware has deleted the schedule reminder, app needs to update the corresponding list data              |      |
| 11             | Firmware has modified the sub-dial style, notifying the app to get it (command_id is 0x33, key is 0x5000)               |      |
| 12             | Firmware notifies iOS to update notification icon and name               |      |
| 13             | Firmware notifies app that the icon has been updated, app needs to get the updated icon status               |      |
| 14             | Firmware requests to reset the weather, app receives it and sends weather data              |      |
| 15             | Steps increase by 2000 steps each time, the device requests app to sync data, and app calls sync interface               |      |
| 16             | Detected sleep ends, requests app to sync sleep data, and app calls sync interface               |      |
| 17             | Firmware modifies Tri-ring data, notifies app to update Tri-ring data               |      |
| 18             | Firmware sends a reminder when fully charged, and the app shows "Device fully charged" on the notification bar               |      |
| 19             | After finishing exercise, manually measuring heart rate, manually measuring blood oxygen, manually measuring stress, the device automatically requests sync, first checks the link state, if not connected, this sync is not executed, then checks if it meets the next automatic sync condition, and requests sync again              |      |
| 20             | Firmware modifies heart rate notification status type, stress notification status type, blood oxygen notification status type, physiological cycle notification status type, health guidance notification status type, reminder notification status type, notifies app to update heart rate, stress, blood oxygen, physiological cycle, health guidance, reminder notification status type              |      |
| 21             | Firmware calculates stress value and notifies app to get the stress value              |      |
| 22             | Firmware notifies app of stress calibration failure (firmware exits measurement interface/detection fails/times out/not worn)              |      |
| 23             | Reserved                                                         |      |
| 24             | Firmware notifies app that BT Bluetooth is connected              |      |
| 25             | Firmware notifies app that BT Bluetooth is disconnected              |      |
| 26             | Firmware notifies that Bluetooth call has started              |      |
| 27             | Firmware notifies that Bluetooth call has ended              |      |
| 28             | New firmware sends a notification command every 4 minutes and 30 seconds to fix the issue of iOS showing offline              |      |
| 29             | Notifies app that exercise has started (applies to intercepting dial transmission like 26)              |      |
| 30             | Notifies app that exercise has ended (applies to intercepting dial transmission like 27)              |      |
| 31             | Firmware restarts and sends a notification to the app (app needs to get firmware version information)              |      |
| 32             | When the device is idle (not using Alexa), it needs to report a notification to the app (time interval is 1 hour)              |      |
| 33             | Firmware finishes organizing space and notifies app to continue downloading dial files              |      |
| 34             | Firmware notifies app to end finding wristband command (corresponding to 6.3 find wristband)              |      |
| 35             | Firmware enters power-saving mode and notifies app              |      |
| 36             | Firmware exits power-saving mode and notifies app              |      |
| ~~37~~             | ~~Firmware notifies app to send GPS hot start parameter settings (deprecated)~~              |      |
| 38             | Firmware completes transferring raw data and notifies app to get feature vector information              |      |
| 39             | Firmware notifies app of blood pressure calibration failure (firmware exits measurement interface/detection fails/times out/not worn)              |      |
| 40             | Firmware completes transferring raw data without feature vector information, notifies app that data collection is finished              |      |
| 41             | Notification of completion of synchronization of V3 health data (for internal use of Android)              |      |
| 42             | Firmware finishes organizing GPS data space and notifies app to send GPS file              |      |
| 43             | Firmware upgrade EPO.dat file failed, notifies app to send the file again              |      |
| 44             | Firmware upgrade EPO.dat file successfully              |      |
| 45             | Firmware upgrade GPS failed, notifies app to transmit again              |      |
| 46             | Firmware upgrade GPS succeeded              |      |
| 47             | When starting exercise, firmware detects GPS abnormality and notifies app              |      |
| 48             | Firmware updates Lembest peripheral information, notifies app to get it              |      |
| 49             | Firmware notifies user to cancel BLE and watch pairing, app handles the pop-up              |      |
| 50             | Firmware notifies app that BT pairing is completed              |      |
| 51             | Firmware sets exercise order, notifies app to get exercise order information              |      |
| 52             | Firmware changes all-day step target parameter, notifies app to get all-day step target (0208)              |      |
| 53             | Firmware notifies app that firmware enters blood pressure calibration interface              |      |
| 54             | Firmware updates automatic recognition switch status, notifies app to get automatic recognition switch status (02EA)              |      |



### 2. Message Type Notification Event:

#### 2.1 Summary:

Description of message type notification events.

#### 2.2 API ID:

````dart
final int? notifyType;
````

#### 2.3 API Parameter Description:

| Decimal Value | Description         |
| ------------- | ------------------- |
| 1             | Alarm has been modified |
| 2             | Firmware overheating exception warning |
| 4             | Display parameter has been modified |
| 8             | Wrist lift parameter has been modified |
| 16            | Do not disturb mode retrieval |
| 32            | Mobile phone volume sent |



### 3. Message ID:

#### 3.1 Summary:

None.

#### 3.2 API ID:

````dart
final int? msgId;
````

#### 3.3 API Parameter Description:

@param: Each message corresponds to an ID



### 4. Quick Message Notification:

#### 4.1 Summary:

None. //// TODO: How to set quick messages

#### 4.2 API ID:

````dart
final int? msgNotice;
````

#### 4.3 API Parameter Description:

| Value | Description                                         |
| ----- | --------------------------------------------------- |
| 0     | None                                                |
| 1     | Custom Message 1 (In a meeting, contact later)      |
| 2     | Custom Message 2                                    |
| 3     | Custom Message 3                                    |
| 4     | Custom Message 4                                    |
| 5     | Custom Message 5                                    |
| ..    | .. (continue up to 10)                              |
| 10    | Custom Message 10                                   |



### 5. Firmware Error Code Notification:

#### 5.1 Summary:

Listens for firmware error code notifications, app retrieves firmware Flash logs.

#### 5.2 API ID:

````dart
final int? errorIndex;
````

#### 5.3 API Parameter Description:

| Value | Error Type                        |
| ----- | --------------------------------- |
| 0     | No error                           |
| 1     | ACC                               |
| 2     | PPG                               |
| 3     | TP                                |
| 4     | FLASH                             |
| 5     | Overheating (PPG)                  |
| 6     | Barometric pressure               |
| 7     | GPS                                |
| 8     | Magnetometer                      |
| 100   | Watchdog reset                      |
| 101   | Power-on reset                      |
| 102   | Software reset                      |
| 103   | OTA reset                           |
| 104   | User-initiated reset                 |
| 105   | Low battery shutdown                 |

Note: 1-100 are firmware error codes, 100-200 are reset log codes.



### 6. Control Event Notification:

#### 6.1 Function Overview:

N/A.

#### 6.2 API ID:

```dart
final int? controlEvt;
```

#### 6.3 API Parameter Description:

| Control Event                            | Event Number |
| ---------------------------------------- | ------------ |
| Control app music play                    | 551          |
| Control app music pause                   | 552          |
| Control app music stop                    | 553          |
| Control app music previous track          | 554          |
| Control app music next track              | 555          |
| Control app take photo (single shot)      | 556          |
| Control app take photo (continuous shot)  | 557          |
| Control app volume up                     | 558          |
| Control app volume down                   | 559          |
| Control app open camera                   | 560          |
| Control app close camera                  | 561          |
| Control app answer phone call             | 562          |
| Control app reject phone call             | 563          |
| Control app music volume (percentage)     | 565          |
| Control app start find my phone           | 570          |
| Control app stop find my phone            | 572          |
| Notify app of anti-lost activation        | 574          |
| Start one-key call in app                 | 575          |
| Notify app of sensor data                 | 576          |
| Notify app of data update                 | 577          |
| Request version check                     | 578          |
| Request OTA update                        | 579          |
| Notify app of SMS information             | 580          |
| Control app camera                        | 581          |
| Notify app of firmware speaker volume     | 591          |



### 7. Control Event Response Parameters:

#### 7.1 Function Overview:

N/A.

#### 7.2 API ID:

```dart
final String? controlJson;
```

#### 7.3 API Parameter Description:

For details of event numbers and corresponding event item content, please refer to [Device Active Notification / Control Events](../../../BaseProtocolEvtExecDoc/en/doc/IDODeviceControlEvt/IDODeviceControlEvtIntroduction.md) //// TODO Optimize the control events that have no parameters