### V3APP获取表盘颜色样式修改

**Flutter示例：**

```dart
//TODO
```



**App收到的json字段**：

| 字段名     | 字段类型 | 字段说明                                             |
| ---------- | -------- | ---------------------------------------------------- |
| version    | int      | 协议库版本号                                         |
| dail_ID    | int      | 表盘ID                                               |
| name       | char []   | 表盘名字 最大30个字节                                |
| dial_type  | int      | 回复类型<br />目前只有 0：无效,1：颜色           |
| style_enum | int      | 颜色改变的枚举 0无效<br />从一开始就是对应的枚举样式 |

`示例：`

```c
{
    "version":0,
    "dail_ID":1,
    "name":"w120.iwf",
    "dial_type":1,
    "style_enum":0
}
```

