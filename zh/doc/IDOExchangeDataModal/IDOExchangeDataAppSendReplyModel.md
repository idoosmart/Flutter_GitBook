# {BLE响应APP发起数据交换的模型说明}

## 1.BLE设备回复APP发送交换运动数据开始模型：

#### 1.1 模型ID

````dart
class IDOAppStartReplyExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 模型成员:

```dart
int? day;             /// 日期
int? hour;            /// 时
int? minute;          /// 分钟
int? second;          /// 秒钟
int? sportType;       /// 运动类型
int? retCode;					/// 0:成功 1:设备已经进入运动模式失败 2:设备电量低失败 
                      /// 3:手环正在充电 4:正在使用Alexa 5:通话中
```



## 2.BLE设备回复APP发送交换运动数据结束模型：

#### 2.1 模型ID

````dart
class IDOAppEndReplyExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 模型成员:

```dart
int? day;             /// 日期
int? hour;            /// 时
int? minute;          /// 分钟
int? second;          /// 秒钟
int? sportType;       /// 运动类型
int? errorCode;       /// 0:成功; 1:设备结束失败
int? calories;        /// 卡路里，单位大卡
int? distance;        /// 距离（单位：米）
int? step;            /// 步数 (单位:步)
int? avgHr;           /// 平均心率
int? maxHr;           /// 最大心率
int? burnFatMins;     /// 脂肪燃烧时长 单位分钟
int? aerobicMins;     /// 心肺锻炼时长 单位分钟
int? limitMins;       /// 极限锻炼时长 单位分钟
```



## 3.BLE设备回复APP交换运动数据过程中模型：

#### 3.1 模型ID

````dart
class IDOAppIngReplyExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 模型成员:

```dart
int? day;             /// 日期
int? hour;            /// 时
int? minute;          /// 分钟
int? second;          /// 秒钟
int? sportType;       /// 运动类型
int? calories;        /// 卡路里 单位大卡
int? distance;        /// 距离 单位0.01km
int? status;          /// 0:全部有效 1:距离无效 2:GPS信号弱
int? step;            /// 步数
int? currentHr;       /// 当前心率
int? interval;        /// 心率间隔 单位秒
int? hrSerial;        /// 序列号
List<int>? hrJson;    /// 心率值数据
```



## 4.BLE设备回复APP发送交换运动数据暂停 模型：

#### 4.1 模型ID

````dart
class IDOAppPauseReplyExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? errCode;                 /// 暂停错误码 0:成功 非0:失败
```



## 5.BLE设备回复APP发送交换运动数据恢复模型：

#### 5.1 模型ID

````dart
class IDOAppRestoreReplyExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? errCode;                 /// 暂停错误码 0:成功 非0:失败
```



## 6.BLE设备回复APP执行V3交换运动数据模型：

#### 6.1 模型ID

````dart
class IDOAppIngV3ReplyExchangeModel extends IDOBaseExchangeModel
````

#### 6.2 模型成员:

```dart
int? day;               /// 日期
int? hour;              /// 时
int? minute;            /// 分钟
int? second;            /// 秒钟
int? sportType;         /// 运动类型
int? version;           /// 协议版本号
int? heartRate;         /// 心率数据
int? distance;          /// 距离 单位根据单位设置的单位显示
int? duration;          /// 持续时间 秒钟
int? realTimeCalories;  /// 动态卡路里
int? realTimeSpeed;     /// 实时速度，单位km/h，扩大100倍
int? kmSpeed;           /// 实时公里配速 单位s/公里
int? steps;             /// 步数
int? swimPosture;       /// 主泳姿
int? status;            /// 状态 0：无效 1：开始 2：手动暂停 3：结束 4：自动暂停
int? realTimeSpeedPace; /// 实时的配速，单位秒，5秒使用滑动平均，第5秒使用1-5秒数据，第6秒使用2-6秒数据

int? trainingEffect;         /// 有氧训练效果等级  单位无  范围 0-50 扩大10倍传输
int? anaerobicTrainingEffect;/// 无氧运动训练效果等级 单位无  范围 0-50 扩大10倍传输

/// 动作类型
/// 1快走
/// 2慢跑
/// 3中速跑
/// 4快跑
/// 5结束课程运动 （还要等待用户是否有自由运动）
/// 6课程结束后自由运动（此字段当operate为5起作用）
/// 运动累积时间=课程内训练时间+课程结束后计时
int? actionType;

/// 需要固件开启功能表
/// action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）
/// action_type = 6时，该字段是课程结束后计时（注：时间递增）
int? countHour;

/// 需要固件开启功能表
/// action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）
/// action_type = 6时，该字段是课程结束后计时（注：时间递增）
int? countMinute;

/// 需要固件开启功能表
/// action_type = 1—5时，该字段是运动倒计时时间（注：时间递减）
/// action_type = 6时，该字段是课程结束后计时（注：时间递增）
int? countSecond;
```



## 7.BLE设备回复APP操作运动计划模型：

#### 7.1 模型ID

````dart
class IDOAppOperatePlanReplyExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 模型成员:

```dart
int? day;          /// 日期
int? hour;         /// 时
int? minute;       /// 分钟
int? second;       /// 秒钟
int? sportType;    /// 运动类型
int? planType;     /// 计划类型：1：跑步计划3km，2：跑步计划5km，3：跑步计划10km，4：半程马拉松训练（二期，5：马拉松训练（二期）

int? operate;      /// 1:开始运动，2：暂停运动, 3:恢复运动 ，4：结束运动, 5: 切换动作
int? actionType;   /// 动作类型 1:快走 2:慢跑 3:中速跑 4:快跑 5:结束课程运动(还要等待用户是否有自由运动) 6:课程结束后自由运动 （此字段当operate为5起作用）

int? errorCode;    /// 0为成功，非0为失败
```
