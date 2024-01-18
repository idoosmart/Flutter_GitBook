# {APP发起数据交换模型说明}

## 1.APP发送交换运动数据开始模型：

#### 1.1 模型ID

````dart
class IDOAppStartExchangeModel extends IDOBaseExchangeModel
````

#### 1.2 模型成员:

```dart
int? day;                  /// 日期
int? hour;                 /// 时
int? minute;               /// 分钟
int? second;               /// 秒钟
int? sportType;            /// 运动类型
int? targetType;           /// 目标类型
int? targetValue;          /// 目标值
int? forceStart;           /// 是否强制开始 0:不强制,1:强制
int? vo2max;               /// 最大摄氧量 单位 ml/kg/min
int? recoverTime;          /// 恢复时长：单位小时
int? avgWeekActivityTime;  /// 上个月平均每周的运动时间 单位分钟
```



## 2.APP发送交换运动数据结束模型：

#### 2.1 模型ID

````dart
class IDOAppEndExchangeModel extends IDOBaseExchangeModel
````

#### 2.2 模型成员:

```dart
int? day;             /// 日期
int? hour;            /// 时
int? minute;          /// 分钟
int? second;          /// 秒钟
int? sportType;       /// 运动类型
int? duration;        /// 持续时长（单位：s）
int? calories;        /// 卡路里，单位大卡
int? distance;        /// 距离（单位：米）
int? isSave;          /// 0:不保存，1:保存
```



## 3.APP交换运动数据过程中模型：

#### 3.1 模型ID

````dart
class IDOAppIngExchangeModel extends IDOBaseExchangeModel
````

#### 3.2 模型成员:

```dart
int? day;             /// 日期
int? hour;            /// 时
int? minute;          /// 分钟
int? second;          /// 秒钟
int? sportType;       /// 运动类型
int? duration;        /// 持续时长 单位s
int? calories;        /// 卡路里 单位大卡
int? distance;        /// 距离 单位0.01km
int? status;          /// 0:全部有效 1:距离无效 2:GPS信号弱
```



## 4.APP发送交换运动数据暂停模型：

#### 4.1 模型ID

````dart
class IDOAppPauseExchangeModel extends IDOBaseExchangeModel
````

#### 4.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
int? pauseHour;               /// 暂停时
int? pauseMinute;             /// 暂停分
int? pauseSecond;             /// 暂停秒
```



## 5.APP发送交换运动数据恢复模型：

#### 5.1 模型ID

````dart
class IDOAppRestoreExchangeModel extends IDOBaseExchangeModel
````

#### 5.2 模型成员:

```dart
int? day;                     /// 日期
int? hour;                    /// 时
int? minute;                  /// 分钟
int? second;                  /// 秒钟
int? sportType;               /// 运动类型
```



## 6.APP执行V3交换运动数据模型：

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
int? signal;            /// 0: 表示信号弱 2: 表示信号强
int? distance;          /// app距离
int? speed;             /// app计算显示实时配速，单位km/h，100倍
int? duration;          /// 持续时间
int? calories;          /// 卡路里
```



## 7.APP操作运动计划模型：

#### 7.1 模型ID

````dart
class IDOAppOperatePlanExchangeModel extends IDOBaseExchangeModel
````

#### 7.2 模型成员:

```dart
int? day;           /// 日期
int? hour;          /// 时
int? minute;        /// 分钟
int? second;        /// 秒钟
int? sportType;     /// 运动类型
int? operate;       /// 1:开始运动 2：暂停运动 3:恢复运动 4：结束运动 5: 切换动作
int? trainingOffset;/// 训练的课程日期偏移 从0开始
int? planType;      /// 计划类型 1:跑步计划3km 2:跑步计划5km 3:跑步计划10km 4:半程马拉松训练(二期) 5:马拉松训练(二期)
```
