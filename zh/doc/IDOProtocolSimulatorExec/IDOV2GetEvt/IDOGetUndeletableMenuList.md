### 获取固件不可删除的快捷应用列表


功能表:getDeletableMenuListV2

**Flutter示例：**

```dart
/// 获取固件不可删除的快捷应用列表事件号
getUnerasableMeunList(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_undeleteable_meun_list
),

/// 获取固件不可删除的快捷应用列表
libManager.send(evt: CmdEvtType.getUnerasableMeunList, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名    | 字段类型 | 字段说明                                                     |
| --------- | -------- | ------------------------------------------------------------ |
| num       | int      | 列表详情个数 最大个数10                                      |
| item_list | int [10] | 不可删除的应用列表<br />0 无效<br />1 步数<br />2 心率<br />3 睡眠<br />4 拍照<br />5 闹钟<br />6 音乐<br />7 秒表<br />8 计时器<br />9 运动模式<br />10 天气<br />11 呼吸锻炼<br />12 查找手机<br />13 压力<br />14 数据三环<br />15 时间界面<br />16 最近一次活动<br />17 健康数据<br />18 血氧 <br />19 菜单设置<br />20 (20)aleax语音依次显示<br />21 X屏（gt01pro-X新增）<br />22 卡路里 （Doro Watch新增）<br />23 距离   （Doro Watch新增）<br />24 一键测量 (IDW05新增)<br />25 renpho health(润丰健康)(IDW12新增) <br />26 指南针 (mp01新增)   <br />27 气压高度计(mp01新增)<br />28 通话列表(蓝牙通话)<br />29 事项提醒<br />30 ICE(紧急联系人咨询)<br />31 最大摄氧量<br />32 恢复时间<br />33 有氧训练效果<br />34 海拔高度<br />35 身体电量<br />36 世界时钟<br />37 语音助手<br />38 AI语音助手<br />39 支付宝<br />40 情绪健康<br />41 生理周期<br />42 环境音量<br />43 睡眠助手<br />44 任务清单 |

`示例：`

```c
{
    "num":4,
    "item_list":[
        1,
        2,
        3,
        4
    ]
}
```
