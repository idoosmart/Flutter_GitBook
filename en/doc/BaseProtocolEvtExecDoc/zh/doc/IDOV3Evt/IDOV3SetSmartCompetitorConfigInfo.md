### V3智能陪跑信息配置


**App下发的json字段**:

| 字段名                | 字段类型 | 字段说明                        |
| --------------------- | -------- | ------------------------------- |
| version               | int      | 协议库版本号 默认0              |
| operate               | int      | 操作 <br />0:无效 1:设置 2:查询 |
| background_font_color | int      | 背景文字颜色 <br />设置操作有效 |
| ai_image_id           | int      | ai形象ID <br />设置操作有效     |
| user_image_id         | int      | 用户形象ID<br />设置操作有效    |
| bg_image_id           | Int      | 背景形象ID<br />设置操作有效    |

`示例：`

```c
{

}
```

**App收到的json字段**：

| 字段名                | 字段类型 | 字段说明                        |
| --------------------- | -------- | ------------------------------- |
| version               | int      | 协议库版本号 默认0              |
| err_code              | int      | 0成功 非0失败                   |
| operate               | int      | 操作 <br />0:无效 1:设置 2:查询 |
| background_font_color | int      | 背景文字颜色 <br />查询操作有效 |
| ai_image_id           | int      | ai形象ID <br />查询操作有效     |
| user_image_id         | int      | 用户形象ID<br />查询操作有效    |
| bg_image_id           | Int      | 背景形象ID<br />查询操作有效    |

`示例：`

```c
{

}
```

