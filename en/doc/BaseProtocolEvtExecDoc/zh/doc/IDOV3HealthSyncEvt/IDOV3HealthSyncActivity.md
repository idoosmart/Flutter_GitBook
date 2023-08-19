#### 同步多运动及跑步课程


**App收到的json字段**：

| 字段名                   | 字段类型 | 字段说明                                                     |
| ------------------------ | -------- | ------------------------------------------------------------ |
| version | int | 协议版本号<br />该条报文的版本号默认0 <br />V3_sync_v3_activity_add_param功能表开启version=16,<br />v3_support_activity_sync_real_time功能表开启version=32 |
| data_length | int | 数据长度<br />固件开启功能表V3_sync_v3_activity_add_param(version=16)或v3_support_activity_sync_real_time(version=32)的情况下该值为0 |
| packet_count | int | 包个数 <br />固件开启功能表V3_sync_v3_activity_add_param(version=16)或v3_support_activity_sync_real_time(version=32)的情况下该值为0 |
| year                     | int      | 数据日期 年  |
| month                    | int      | 数据日期 月                                                  |
| day                      | int      | 数据日期 日                                                  |
| hour                     | int      | 数据日期 时                                                  |
| minute                   | int      | 数据日期 分                                                  |
| second                   | int      | 数据日期 秒                                                  |
| type                     | int      | 运动枚举                             |
| connect_app              | int      | 手环是否连接app，用app评产生何种报告<br />1是连接，0是未连接 |
| sport_start_type         | int      | 0:无效， 1 : app发起的运动， 2：手表发起的运动               |
| hr_data_interval_minute  | int      | 心率数据间隔  单位分钟                                       |
| step                     | int      | 步数                                                         |
| durations                | int      | 运动时长 单位： s                                            |
| calories                 | int      | 卡路里 单位：千卡                                            |
| distance                 | int      | 距离 单位： m                                                |
| avg_hr_value             | int      | 平均心率值                                                   |
| max_hr_value             | int      | 最大心率值                                                   |
| min_hr_value             | Int      | 最小心率值<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| avg_step_frequency       | int      | 平均步频 步/分钟                                             |
| max_step_frequency       | int      | 最大步频 步/分钟                                             |
| avg_step_stride          | int      | 平均步幅                                                     |
| max_step_stride          | int      | 最大步幅                                                     |
| avg_speed                | int      | 平均速度  km/h  固件是 扩大100倍                             |
| max_speed                | int      | 最快速度  km/h  固件是 扩大100倍                             |
| avg_pace_speed           | int      | 平均配速 传过来的是s钟<br /> 比如361  361/60=6分 余数是1s  6''1'  , 公里和英里是按照 英里= 公里*1609/1000f<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| max_pace_speed          | int      | 最快配速<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| avg_km_speed     | int      | 平均公里配速 传过来的是s钟<br /> 比如361  361/60=6分 余数是1s  6''1'  , 公里和英里是按照 英里= 公里*1609/1000f |
| max_km_speed            | int      | 最快公里配速                                                 |
| warm_up_mins   | int      | 热身运动的累计时长  分钟部分                                 |
| fat_burning_mins | int      | 脂肪燃烧的累计时长  分钟部分                                 |
| aerobic_exercise_mins | int      | 有氧运动的累计时长  分钟部分                                 |
| anaerobic_exercise_mins | int      | 无氧运动的累计时长  分钟部分                                 |
| extreme_exercise_mins | int      | 极限锻炼的累计时长  分钟部分                                 |
| warm_up_sec  | int      | 热身运动的累计时长  秒钟部分                                 |
| fat_burning_sec | int      | 脂肪燃烧的累计时长  秒钟部分                                 |
| aerobic_exercise_sec | int      | 有氧运动的累计时长  秒钟部分                                 |
| anaerobic_exercise_sec | int      | 无氧运动的累计时长  秒钟部分                                 |
| extreme_exercise_sec | Int      | 极限锻炼的累计时长  秒钟部分                                 |
| vO2max                   | Int      | 最大摄氧量 单位：毫升/公斤/分钟<br />范围  0-80  不放大100倍 （该字段在前） |
| grade                    | Int      | 摄氧量等级 <br />1：低等   2：业余   3：一般  <br />4：平均   5：良好   6：优秀   7：专业   <br />v3_support_sports_plan或v3_oxygen_data_support_grade固件开启则有效否则为0，为0则不支持摄氧量等级 |
| recovery_time_year       | int      | 恢复时间点年<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| recovery_time_mon        | int      | 恢复时间点月<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| recovery_time_day        | int      | 恢复时间点日<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| recovery_time_hour       | int      | 恢复时间点时<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| recovery_time_min        | int      | 恢复时间点分<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| recovery_time_s          | int      | 恢复时间点秒<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| training_effect | int | 训练效果 单位：无 范围： 1.0 - 5.0 （扩大10倍传输）<br />V3_sync_v3_activity_add_param/v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| mi_speed_count           | int      | 英里配速个数                                                 |
| hr_item_count            | int      | 心率个数                                                     |
| activity_data_item_count | int      | 洪堡定制数据字段详情个数，一分钟存一个                       |
| km_speed_count           | int      | 公里配速的个数 最大100                                       |
| mi_speed_count   | int      | 英里配速个数                                                 |
| pace_count               | int      | 实时配速个数<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| frequency_count          | int      | 步频个数                                                     |
| paddle_number_count      | int      | 桨次个数  <br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| paddle_frequency_count   | int      | 桨频个数 <br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| tread_frequency_count    | int      | 踏频个数 <br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| real_speed_count | int | 实时速度个数<br />v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| end_month                | int      | 运动结束时间 月<br />考虑到运动后用户暂停运动，导致运动结束后运动结束时间与app的运动结束时间有差异，此时的运动结束时间由固件返回，不支持该协议的返回0即可  app判断月份是否为0判断是否采用以下字段作为运动结束时间<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| end_day                  | int      | 运动结束时间 日<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| end_hour                 | int      | 运动结束时间 时<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| end_minute               | int      | 运动结束时间 分<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| training_offset | int | 训练的课程日期偏移 从零开始<br />v3_support_sports_plan功能表未开启的时候返回0 |
| act_type | int | 计划类型：<br />1:跑步计划3km<br />2:跑步计划5km<br />3:跑步计划10km<br />4:半程马拉松训练（二期）<br />5:马拉松训练（二期）  <br />64:6分钟轻松跑<br />65:10分钟轻松跑<br />66:15分钟轻松跑<br />67:走跑结合初级<br />68:走跑结合进阶<br />69:走跑结合强化<br />70:跑后拉伸<br />v3_support_sports_plan功能表未开启的时候返回0 |
| in_class_calories | int | 课程内运动热量 单位千卡                                      |
| completion_rate | int | 动作完成率 0—100 |
| hr_completion_rate | int | 心率控制率 0—100 |
| smart_competitor | int | 0:无效 1:非智能陪跑运动 2:智能陪跑运动<br />功能表support_smart_competitor开启有效|
| ai_image_id | int | ai形象ID<br />功能表support_smart_competitor开启有效|
| user_image_id | int | 用户形象ID<br />功能表support_smart_competitor开启有效|
| bg_image_id | int | 背景形象ID<br />功能表support_smart_competitor开启有效|
| smart_competitor_pace | int | 智能陪跑对手配速<br />功能表support_smart_competitor开启有效|
| warm_up_performance | int | 热身表现 0-100 <br />v3_support_sports_plan & support_warm_up_before_running开启有效 |
| gps_status | int | GPS状态 <br />0:无效 1:开启 2:未开启(未开启时展示`距离` 开启则展示`3D距离`)<br />v3_support_sports_plan & version=0x30时有效 |
| distance3d | int | 3d距离 单位米<br />support_sync_activity_data_3d_distance_speed & v3_support_sports_plan & version=0x30时有效 |
| avg_3d_speed | int | 平均3d速度 单位km/h <br />app收到需要/100 扩大100倍传<br />support_sync_activity_data_3d_distance_speed & v3_support_sports_plan & version=0x30时有效 |
| avg_vertical_speed | int | 平均垂直速度 单位m/h <br />app收到需要/10  扩大10倍传<br />support_sync_activity_data_3d_distance_speed & v3_support_sports_plan & version=0x30时有效 |
| avg_slope | int | 平均坡度 单位度 <br />-90 ~ 90<br />support_sync_activity_data_avg_slope & v3_support_sports_plan & version=0x30时有效 |
| max_altitude | int | 最高海拔高度 单位米<br />-500 ~ 9000<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| mix_altitude | int | 最低海拔高度 单位米<br />-500 ~ 9000<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| cumulative_altitude_rise | int | 累计海拔上升 单位米<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| cumulative_altitude_loss | int | 累计海拔下降 单位米<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| altitude_count | int | 海拔高度详情个数<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| avg_altitude | int | 平均海拔高度 单位米 <br />-500 ~ 9000<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| act_count | int | 动作详情个数 |
| hr_data_vlaue            | int []   | 心率数据详情                                                 |
| frequency_items          | int []  | 步频数据详情                                                 |
| items_mi_speed           | int [] | 英里配速详情                                                 |
| pace_speed_items         | int [] | 实时配速详情<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| paddle_number_items      | int []  | 桨次详情<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| paddle_frequency_items   | int []  | 桨频详情<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| tread_frequency_items    | int []  | 踏频详情<br />V3_sync_v3_activity_add_param或v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| act_items | int [] | 动作详情<br />v3_support_sports_plan功能表未开启的时候返回0 |
| item_real_speed_temp | int [] | 实时速度详情<br />v3_support_sports_plan功能表开启时返回0<br />v3_support_activity_sync_real_time功能表未开启的时候返回0 |
| altitude_item | int [] | 海拔高度数据 单位米 范围-500~9000<br />support_sync_activity_data_altitude_info & v3_support_sports_plan & version=0x30时有效 |
| items | 集合 | 洪堡定制字段数据详情，steps & calories & distance的集合 |
| items_km_speed | 集合 | 公里配速数据详情，second的集合 |

| 字段名   | 字段类型 | 字段说明 |
| -------- | -------- | -------- |
| steps    | int      | 步频     |
| calories | int      | 卡路里   |
| distance | int      | 距离     |

| 字段名 | 字段类型 | 字段说明 |
| ------ | -------- | -------- |
| second | int      | 公里配速 |

`示例：`

```c
{
    "act_type" : 0,
    "action_temp" : null,
    "activity_data_item_count" : 0,
    "aerobic_exercise_mins" : 0,
    "aerobic_exercise_sec" : 0,
    "anaerobic_exercise_mins" : 0,
    "anaerobic_exercise_sec" : 0,
    "avg_hr_value" : 0,
    "avg_km_speed" : 0,
    "avg_pace_speed" : 0,
    "avg_speed" : 0,
    "avg_step_frequency" : 0,
    "avg_step_stride" : 0,
    "calories" : 0,
    "completion_rate" : 0,
    "connect_app" : 0,
    "data_length" : 0,
    "day" : 0,
    "distance" : 0,
    "durations" : 0,
    "end_day" : 0,
    "end_hour" : 0,
    "end_minute" : 0,
    "end_month" : 0,
    "extreme_exercise_mins" : 0,
    "extreme_exercise_sec" : 0,
    "fat_burning_mins" : 0,
    "fat_burning_sec" : 0,
    "frequency_count" : 0,
    "frequency_items" : null,
    "grade" : 0,
    "hour" : 0,
    "hr_completion_rate" : 0,
    "hr_data_interval_minute" : 0,
    "hr_data_vlaue" : null,
    "hr_item_count" : 0,
    "in_class_calories" : 0,
    "item_real_speed_temp" : null,
    "items" : null,
    "items_km_speed" : null,
    "items_mi_speed" : null,
    "km_speed_count" : 0,
    "max_hr_value" : 0,
    "max_km_speed" : 0,
    "max_pace_speed" : 0,
    "max_speed" : 0,
    "max_step_frequency" : 0,
    "max_step_stride" : 0,
    "mi_speed_count" : 0,
    "min_hr_value" : 0,
    "minute" : 0,
    "month" : 0,
    "pace_count" : 0,
    "pace_speed_items" : null,
    "packet_count" : 0,
    "paddle_frequency_count" : 0,
    "paddle_frequency_items" : null,
    "paddle_number_count" : 0,
    "paddle_number_items" : null,
    "real_speed_count" : 0,
    "recovery_time_day" : 0,
    "recovery_time_hour" : 0,
    "recovery_time_min" : 0,
    "recovery_time_mon" : 0,
    "recovery_time_s" : 0,
    "recovery_time_year" : 0,
    "second" : 0,
    "sport_start_type" : 0,
    "step" : 0,
    "training_effect" : 0,
    "training_offset" : 0,
    "tread_frequency_count" : 0,
    "tread_frequency_items" : null,
    "type" : 0,
    "vO2max" : 0,
    "version" : 0,
    "warm_up_mins" : 0,
    "warm_up_sec" : 0,
    "year" : 0
}
```
