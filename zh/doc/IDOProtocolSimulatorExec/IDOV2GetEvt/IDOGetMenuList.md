### 获取设备支持的菜单列表


功能表:getMenuList

**Flutter示例：**

```dart
/// 获取设备支持的列表事件号
getMenuList(
  evtBase: _VBusEvtBase.base_app_get,
  evtType: _VBusEvtType.app_get_menu_list),

/// 获取设备支持的列表
libManager.send(evt: CmdEvtType.getMenuList, json: jsonEncode(json));
```



**App收到的json字段**：

| 字段名           | 字段类型 | 字段说明                                        |
| ---------------- | -------- | ----------------------------------------------- |
| min_show_num     | int      | 最小显示个数                                    |
| max_show_num     | int      | 最大显示个数                                    |
| max_num          | int      | 目前列表最大个数                                |
| current_show_num | int      | 设备当前显示的列表个数                          |
| items            | 集合     | 设备当前显示的列表详情<br />index & value的集合 |

| 字段名 | 字段类型 | 字段说明                                                     |
| ------ | -------- | ------------------------------------------------------------ |
| index  | int      | 序号<br />0开始 最大值13                                     |
| value  | int      | 类型<br />0 无效<br />1 步数<br />2 心率<br />3 睡眠<br />4 拍照<br />5 闹钟<br />6 音乐 <br />7 秒表 <br />8 计时器<br />9 运动模式<br />10 天气<br />11 呼吸锻炼<br />12 查找手机<br />13 压力<br />14 数据三环<br />15 时间界面 <br />16 最近一次活动 <br />17 健康数据 <br />18 血氧  <br />19 菜单设置 <br />20 (20)aleax语音依次显示 <br />21 X屏（gt01pro-X新增）<br />22 卡路里 （Doro Watch新增）<br />23 距离   （Doro Watch新增）<br />24 一键测量 (IDW05新增)  <br />25 renpho health(润丰健康)(IDW12新增) <br />26 指南针 (mp01新增)  <br />27 气压高度计(mp01新增) |

`示例：`

```c
{
  "current_show_num" : 5,
  "items" :
  [
    {
      "index" : 0,
      "value" : 17

    },
    {
      "index" : 1,
      "value" : 2
    },
    {
      "index" : 2,
      "value" : 13
    },
    {
      "index" : 3,
      "value" : 16
    },
    {
      "index" : 4,
      "value" : 20
    },
    {
      "index" : 5,
      "value" : 6
    },
    {
      "index" : 6,
      "value" : 10
    }
  ],
  "max_num" : 7,
  "max_show_num" : 7,
  "min_show_num" : 2
}
```

