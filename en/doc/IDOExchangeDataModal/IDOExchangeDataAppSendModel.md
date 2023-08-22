# {APP Data Exchange Model Specification}

## 1. Model for APP Start Exchange of Sports Data:

#### 1.1 Model ID

````dart
class IDOAppStartExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 Model Members:

```dart
int? day;                  /// Date
int? hour;                 /// Hour
int? minute;               /// Minute
int? second;               /// Second
int? sportType;            /// Sport type
int? targetType;           /// Target type
int? targetValue;          /// Target value
int? forceStart;           /// Whether to force start. 0: No, 1: Yes
int? vo2max;               /// Maximum oxygen uptake. Unit: ml/kg/min
int? recoverTime;          /// Recovery time. Unit: hours
int? avgWeekActivityTime;  /// Average weekly activity time of last month. Unit: minutes
```



## 2. Model for APP End Exchange of Sports Data:

#### 2.1 Model ID

````dart
class IDOAppEndExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 Model Members:

```dart
int? day;             /// Date
int? hour;            /// Hour
int? minute;          /// Minute
int? second;          /// Second
int? sportType;       /// Sport type
int? duration;        /// Duration (in seconds)
int? calories;        /// Calories. Unit: kcal
int? distance;        /// Distance. Unit: meters
int? isSave;          /// 0: Do not save, 1: Save
```



## 3. Model for APP During Exchange of Sports Data:

#### 3.1 Model ID

````dart
class IDOAppIngExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 Model Members:

```dart
int? day;             /// Date
int? hour;            /// Hour
int? minute;          /// Minute
int? second;          /// Second
int? sportType;       /// Sport type
int? duration;        /// Duration in seconds
int? calories;        /// Calories. Unit: kcal
int? distance;        /// Distance. Unit: 0.01km
int? status;          /// 0: All valid, 1: Distance invalid, 2: Weak GPS signal
```



## 4. Model for APP Pause Exchange of Sports Data:

#### 4.1 Model ID

````dart
class IDOAppPauseExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport type
int? pauseHour;               /// Pause hour
int? pauseMinute;             /// Pause minute
int? pauseSecond;             /// Pause second
```



## 5. Model for APP Restore Exchange of Sports Data:

#### 5.1 Model ID

````dart
class IDOAppRestoreExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport type
```



## 6. Model for APP Execution of V3 Exchange of Sports Data:

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
int? signal;            /// 0: Weak signal, 2: Strong signal
int? distance;          /// App distance
int? speed;             /// Real-time pace calculated and displayed by the app. Unit: km/h, multiplied by 100
int? duration;          /// Duration
int? calories;          /// Calories
```



## 7. Model for APP Operation of Sports Plan:

#### 7.1 Model ID

````dart
class IDOAppOperatePlanExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 Model Members:

```dart
int? day;           /// Date
int? hour;          /// Hour
int? minute;        /// Minute
int? second;        /// Second
int? sportType;     /// Sport type
int? operate;       /// 1: Start sport, 2: Pause sport, 3: Resume sport, 4: End sport, 5: Switch action
int? trainingOffset;/// Training course date offset. Starting from 0.
int? planType;      /// Plan type. 1: Running plan 3km, 2: Running plan 5km, 3: Running plan 10km, 4: Half marathon training (Phase 2), 5: Marathon training (Phase 2)
```
请注意，以上翻译仅为文本内容的翻译，不包括代码的逻辑解释。