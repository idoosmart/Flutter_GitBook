# Explanation of the Model for BLE Device Responding to APP's Data Exchange Request

## 1. Model for BLE Device Reply to APP's Start Data Exchange Request:

#### 1.1 Model ID

````dart
class IDOAppStartReplyExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 Model Members:

```dart
int? day;             /// Date
int? hour;            /// Hour
int? minute;          /// Minute
int? second;          /// Second
int? sportType;       /// Sport type
int? retCode;                   /// 0: Success 1: Device failed to enter exercise mode 
                      /// 2: Low battery level of device failed 3: Bracelet is charging 
                      /// 4: Using Alexa 5: In call
```



## 2. Model for BLE Device Reply to APP's End Data Exchange Request:

#### 2.1 Model ID

````dart
class IDOAppEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 Model Members:

```dart
int? day;             /// Date
int? hour;            /// Hour
int? minute;          /// Minute
int? second;          /// Second
int? sportType;       /// Sport type
int? errorCode;       /// 0: Success; 1: Device failed to end exercise
int? calories;        /// Calories, in kilocalories
int? distance;        /// Distance in meters
int? step;            /// Number of steps
int? avgHr;           /// Average heart rate
int? maxHr;           /// Maximum heart rate
int? burnFatMins;     /// Duration of fat burning exercise in minutes
int? aerobicMins;     /// Duration of aerobic exercise in minutes
int? limitMins;       /// Duration of limit exercise in minutes
```



## 3. Model for BLE Device Reply to APP During Data Exchange Process:

#### 3.1 Model ID

````dart
class IDOAppIngReplyExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 Model Members:

```dart
int? day;             /// Date
int? hour;            /// Hour
int? minute;          /// Minute
int? second;          /// Second
int? sportType;       /// Sport type
int? calories;        /// Calories in kilocalories
int? distance;        /// Distance in kilometers
int? status;          /// 0: All data valid 1: Distance invalid 2: Weak GPS signal
int? step;            /// Number of steps
int? currentHr;       /// Current heart rate
int? interval;        /// Heart rate interval in seconds
int? hrSerial;        /// Serial number
List<int>? hrJson;    /// Heart rate data in JSON format
```



## 4. Model for BLE Device Reply to APP's Pause Data Exchange Request:

#### 4.1 Model ID

````dart
class IDOAppPauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport type
int? errCode;                 /// Pause error code 0: Success, non-zero: Failed
```



## 5. Model for BLE Device Reply to APP's Resume Data Exchange Request:

#### 5.1 Model ID

````dart
class IDOAppRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport type
int? errCode;                 /// Resume error code 0: Success, non-zero: Failed
```



## 6. Model for BLE Device Reply to APP for V3 Data Exchange:

#### 6.1 Model ID

````dart
class IDOAppIngV3ReplyExchangeModel extends IDOBaseExchangeModel
````

#### 6.2 Model Members:

```dart
int? day;               /// Date
int? hour;              /// Hour
int? minute;            /// Minute
int? second;            /// Second
int? sportType;         /// Sport type
int? version;           /// Protocol version
int? heartRate;         /// Heart rate data
int? distance;          /// Distance in user-defined unit
int? duration;          /// Duration in seconds
int? realTimeCalories;  /// Dynamic calories
int? realTimeSpeed;     /// Real-time speed, unit: km/h, scaled by 100
int? kmSpeed;           /// Real-time pace per kilometer, unit: seconds/km
int? steps;             /// Number of steps
int? swimPosture;       /// Main swimming posture
int? status;            /// Status 0: Invalid 1: Start 2: Manually pause 3: End 4: Auto pause
int? realTimeSpeedPace; /// Real-time pace, unit: seconds, 5 seconds using sliding average, 
                        /// 5th second using data from 1-5s, 6th second using data from 2-6s

int? trainingEffect;         /// Aerobic training effect level  Unit: None  Range: 0-50, scaled by 10
int? anaerobicTrainingEffect;/// Anaerobic training effect level Unit: None  Range: 0-50, scaled by 10

/// Action type
/// 1: Fast walking
/// 2: Jogging
/// 3: Moderate running
/// 4: Fast running
/// 5: End course exercise (waiting for user to perform free exercise)
/// 6: Free exercise after course ends (this field is effective when operate=5)
/// Sport accumulation time = Training time within the course + Timing after the course ends
int? actionType;

/// Requires firmware to enable function
/// When action_type = 1-5, this field is the countdown time of exercise (decreasing time)
/// When action_type = 6, this field is the timing after the course ends (increasing time)
int? countHour;

/// Requires firmware to enable function
/// When action_type = 1-5, this field is the countdown time of exercise (decreasing time)
/// When action_type = 6, this field is the timing after the course ends (increasing time)
int? countMinute;

/// Requires firmware to enable function
/// When action_type = 1-5, this field is the countdown time of exercise (decreasing time)
/// When action_type = 6, this field is the timing after the course ends (increasing time)
int? countSecond;
```



## 7. Model for BLE Device Reply to APP's Operation on Exercise Plan:

#### 7.1 Model ID

````dart
class IDOAppOperatePlanReplyExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Sport type
int? planType;     /// Plan type: 1: 3km running plan, 2: 5km running plan, 
                   /// 3: 10km running plan, 4: Half marathon training (Phase II), 
                   /// 5: Marathon training (Phase II)

int? operate;      /// 1: Start exercise, 2: Pause exercise, 3: Resume exercise, 4: End exercise, 5: Switch action
int? actionType;   /// Action type: 1: Fast walking, 2: Jogging, 3: Moderate running, 
                   /// 4: Fast running, 5: End course exercise (waiting for user to perform free exercise), 
                   /// 6: Free exercise after course ends (this field is effective when operate=5)

int? errorCode;    /// 0 for success, non-zero for failure
```