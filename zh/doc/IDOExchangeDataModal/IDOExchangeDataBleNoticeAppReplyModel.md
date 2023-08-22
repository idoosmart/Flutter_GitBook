# {App回复BLE设备发起交换运动的模型说明}

## 1.APP回复BLE设备发送交换运动数据开始模型：

#### 1.1 模型ID

````dart
class IDOBleStartReplyExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? operate;                 /// 1:请求app打开gps 2:发起运动请求
int? retCode;                 /// 0:成功 非0失败
```



## 2.APP回复BLE设备交换运动数据过程中模型：

#### 2.1 模型ID

````dart
class IDOBleIngReplyExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? distance;                /// 距离 单位：0.01km
```



## 3.APP回复BLE设备发送交换运动数据结束模型：

#### 3.1 模型ID

````dart
class IDOBleEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? retCode;                 /// 0:成功 非0失败
```



## 4.APP回复BLE设备发送交换运动数据暂停模型：

#### 4.1 模型ID

````dart
class IDOBlePauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? retCode;                 /// 0:成功 非0失败
```



## 5.APP回复BLE设备发送交换运动数据恢复模型：

#### 5.1 模型ID

````dart
class IDOBleRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? retCode;                 /// 0:成功 非0失败
```



## 6.APP回复BLE设备操作运动计划模型：

#### 6.1 模型ID

````dart
class IDOBleOperatePlanReplyExchangeModel extends IDOBaseExchangeModel
````

#### 6.2 模型成员:

```dart
int? day;       /// 日期
int? hour;      /// 时
int? minute;    /// 分钟
int? second;    /// 秒钟
int? sportType; /// 运动类型
int? operate;   /// 1:开始运动 2：暂停运动 3:恢复运动 4:结束运动 5:切换动作
int? planType;  /// 计划类型 1:跑步计划3km 2:跑步计划5km 3:跑步计划10km 4:半程马拉松训练(二期) 5:马拉松训练(二期)

int? actionType;/// 动作类型 1:快走 2:慢跑 3:中速跑 4:快跑 5:结束课程运动(还要等待用户是否有自由运动) 6:课程结束后自由运动(此字段当operate为5起作用)

int? errorCode;/// 0为成功，非0为失败
```



## 7.APP回复BLE设备通知交换运动数据暂停模型(APP发起的运动)：

#### 7.1 模型ID

````dart
class IDOAppBlePauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 模型成员:

```dart
int? day;          /// 日期
int? hour;         /// 时
int? minute;       /// 分钟
int? second;       /// 秒钟
int? sportType;    /// 运动类型
int? errorCode;    /// 0:成功 1:没有进入运动模式失败
```



## 8.APP回复BLE设备通知交换运动数据恢复模型(APP发起的运动)：

#### 8.1 模型ID

````dart
class IDOAppBleRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 8.2 模型成员:

```dart
int? day;          /// 日期
int? hour;         /// 时
int? minute;       /// 分钟
int? second;       /// 秒钟
int? sportType;    /// 运动类型
int? errorCode;    /// 0:成功 1:没有进入运动模式失败
```



## 9.APP回复BLE设备通知交换运动数据结束模型(APP发起的运动)：

#### 9.1 模型ID

````dart
class IDOAppBleEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 9.2 模型成员:

```dart
int? day;          /// 日期
int? hour;         /// 时
int? minute;       /// 分钟
int? second;       /// 秒钟
int? sportType;    /// 运动类型
int? errorCode;    /// 0:成功 1:没有进入运动模式失败
int? duration;     /// 持续时长 单位s
int? calories;     /// 卡路里 单位大卡
int? distance;     /// 距离 单位0.01km
```

