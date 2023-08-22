# {App Reply Exchange Model for BLE Device Initiating Movement}

## 1. Model ID for App Reply to BLE Device Sending Exchange Movement Data Initiation:

#### 1.1 Model ID

````dart
class IDOBleStartReplyExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport Type
int? operate;                 /// 1: Request app to enable GPS 2: Initiating movement request
int? retCode;                 /// 0: Success, non-zero: Failure
```



## 2. Model for App Reply to BLE Device during Exchange of Movement Data:

#### 2.1 Model ID

````dart
class IDOBleIngReplyExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport Type
int? distance;                /// Distance in 0.01 km unit
```



## 3. Model for App Reply to BLE Device sending Exchange Movement Data End:

#### 3.1 Model ID

````dart
class IDOBleEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport Type
int? retCode;                 /// 0: Success, non-zero: Failure
```



## 4. Model for App Reply to BLE Device Sending Exchange Movement Data Pause:

#### 4.1 Model ID

````dart
class IDOBlePauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport Type
int? retCode;                 /// 0: Success, non-zero: Failure
```



## 5. Model for App Reply to BLE Device Sending Exchange Movement Data Restore:

#### 5.1 Model ID

````dart
class IDOBleRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 Model Members:

```dart
int? day;                     /// Date
int? hour;                    /// Hour
int? minute;                  /// Minute
int? second;                  /// Second
int? sportType;               /// Sport Type
int? retCode;                 /// 0: Success, non-zero: Failure
```



## 6. Model for App Reply to BLE Device Operating Movement Plan:

#### 6.1 Model ID

````dart
class IDOBleOperatePlanReplyExchangeModel extends IDOBaseExchangeModel
````

#### 6.2 Model Members:

```dart
int? day;       /// Date
int? hour;      /// Hour
int? minute;    /// Minute
int? second;    /// Second
int? sportType; /// Sport Type
int? operate;   /// 1: Start movement 2: Pause movement 3: Resume movement 4: End movement 5: Switch action
int? planType;  /// Plan type 1: 3km running plan 2: 5km running plan 3: 10km running plan 4: Half marathon training (Phase 2) 5: Marathon training (Phase 2)

int? actionType;/// Action type 1: Fast walking 2: Slow running 3: Medium speed running 4: Fast running 5: End course movement (waiting for user's free movement) 6: Free movement after course ends (this field works when operate is 5)

int? errorCode;/// 0 for success, non-zero for failure
```



## 7. Model for App Reply to BLE Device Notifying Exchange Movement Data Pause (Movement initiated by the app):

#### 7.1 Model ID

````dart
class IDOAppBlePauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Sport Type
int? errorCode;    /// 0: Success 1: Failure to enter movement mode
```



## 8. Model for App Reply to BLE Device Notifying Exchange Movement Data Restore (Movement initiated by the app):

#### 8.1 Model ID

````dart
class IDOAppBleRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 8.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Sport Type
int? errorCode;    /// 0: Success 1: Failure to enter movement mode
```



## 9. Model for App Reply to BLE Device Notifying Exchange Movement Data End (Movement initiated by the app):

#### 9.1 Model ID

````dart
class IDOAppBleEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 9.2 Model Members:

```dart
int? day;          /// Date
int? hour;         /// Hour
int? minute;       /// Minute
int? second;       /// Second
int? sportType;    /// Sport Type
int? errorCode;    /// 0: Success 1: Failure to enter movement mode
int? duration;     /// Duration in seconds
int? calories;     /// Calories in kilocalories
int? distance;     /// Distance in 0.01 km unit
```