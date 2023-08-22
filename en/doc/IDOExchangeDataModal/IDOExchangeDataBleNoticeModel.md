# {BLE Data Exchange Model Specification}

## 1. BLE Device Sends Start of Data Exchange for Exercise Model:

#### 1.1 Model ID

````dart
class IDOBleIngExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Exercise Type
int? operate;                 /// 1: Request app to enable GPS, 2: Initiates exercise request
```



## 2. BLE Device Data Exchange in Progress for Exercise Model:

#### 2.1 Model ID

````dart
class IDOBleIngExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Exercise Type
int? distance;                /// Distance in 0.01km units
```



## 3. BLE Device Sends End of Data Exchange for Exercise Model:

#### 3.1 Model ID

````dart
class IDOBleEndExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Exercise Type
```



## 4. BLE Device Sends Pause Data Exchange for Exercise Model:

#### 4.1 Model ID

````dart
class IDOBlePauseExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Exercise Type
```



## 5. BLE Device Sends Resume Data Exchange for Exercise Model:

#### 5.1 Model ID

````dart
class IDOBleRestoreExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Exercise Type
```



## 6. BLE Device Operates Exercise Plan Model:

#### 6.1 Model ID

````dart
class IDOBleOperatePlanExchangeModel extends IDOBaseExchangeModel
````

#### 6.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Exercise Type
int? operate;      /// 1: Start exercise, 2: Pause exercise, 3: Resume exercise, 4: End exercise, 5: Switch action
int? planType;     /// Plan type 1: 3km running plan, 2: 5km running plan, 3: 10km running plan, 4: Half marathon training (Phase 2), 5: Marathon training (Phase 2)

int? actionType;   /// Action type 1: Fast walking; 2: Slow jogging; 3: Moderate running; 4: Fast running; 5: End of course exercise (waiting for user to choose free exercise); 6: Free exercise after course ends (this field is applicable when operate is 5)

int? errorCode;    /// 0 means success, non-zero means failure
int? trainingYear; /// Training course year
int? trainingMonth;/// Training course month
int? trainingDay;  /// Training course day
int? time;         /// Action target time in seconds
int? lowHeart;     /// Lower range of heart rate
int? highHeart;    /// Upper range of heart rate
```



## 7. BLE Device Notifies Pause of Data Exchange for Exercise Model (Exercise initiated by App):

#### 7.1 Model ID

````dart
class IDOAppBlePauseExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Exercise Type
```



## 8. BLE Device Notifies Resume of Data Exchange for Exercise Model (Exercise initiated by App):

#### 8.1 Model ID

````dart
class IDOAppBleRestoreExchangeModel extends IDOBaseExchangeModel
````

#### 8.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Exercise Type
```



## 9. BLE Device Notifies End of Data Exchange for Exercise Model (Exercise initiated by App):

#### 9.1 Model ID

````dart
class IDOAppBleRestoreExchangeModel extends IDOBaseExchangeModel
````

#### 9.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Exercise Type
int? duration;     /// Duration in seconds
int? calories;     /// Calories in kcal
int? distance;     /// Distance in 0.01km units
int? avgHr;        /// Average heart rate
int? maxHr;        /// Maximum heart rate
int? burnFatMins;  /// Fat burning duration in minutes
int? aerobicMins;  /// Aerobic exercise duration in minutes
int? limitMins;    /// Maximum exercise duration in minutes
int? isSave;       /// 0: Do not save, 1: Save
```