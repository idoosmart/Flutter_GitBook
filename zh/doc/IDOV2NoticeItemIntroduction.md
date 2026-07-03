# IDO 通知中心开关 notify_item 位定义说明

在设置或获取通知中心状态时，`notify_item1` 到 `notify_item16` 的每个字段代表一个 8 位字节（在 JSON 传输中表现为 0~255 的整数）。

根据 **C 库底层协议规范及协议文档** 的权威定义，所有的 `notify_item` 开关都是**正向位映射**（即 Bit 0 对应最低位二进制 `1 shl 0`，Bit 7 对应最高位二进制 `1 shl 7`）。

> [!NOTE]
> - **开关值**：`0` 表示关闭，`1` 表示开启。
> - **C 库 V3 协议命名对应**：在底层 C 语言的 V3 消息提醒协议中（命令字 `0x33`），用户看到的结构体 `protocol_v3_msg_notify_remind_data_decode_reply` 里的 `notify_item1`（对应 google_messages 等）和 `notify_item2`（对应 buzud），在 SDK 暴露给 Flutter 的 JSON 接口中，被统一映射为了 `notify_item15` 和 `notify_item16`。

---

## 一、 notify_item 1 ~ 16 各位十进制权重

在字节中，各位的十进制权重如下（与常规位运算习惯一致）：
- **Bit 7** = 0x80 (128)
- **Bit 6** = 0x40 (64)
- **Bit 5** = 0x20 (32)
- **Bit 4** = 0x10 (16)
- **Bit 3** = 0x08 (8)
- **Bit 2** = 0x04 (4)
- **Bit 1** = 0x02 (2)
- **Bit 0** = 0x01 (1)

---

## 二、 详细位映射列表

### notify_item1
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | twitter (Twitter) |
| Bit 6 | 64 | facebook (Facebook) |
| Bit 5 | 32 | weibo (微博) |
| Bit 4 | 16 | qq (QQ) |
| Bit 3 | 8 | wechat (微信) |
| Bit 2 | 4 | email (邮件) |
| Bit 1 | 2 | message (短信) |
| Bit 0 | 1 | 保留/无效 |

### notify_item2
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | other (其他) |
| Bit 6 | 64 | alarmClock (闹钟事件) |
| Bit 5 | 32 | skype (Skype) |
| Bit 4 | 16 | calendar (日历事件) |
| Bit 3 | 8 | linked_in (LinkedIn) |
| Bit 2 | 4 | instagram (Instagram) |
| Bit 1 | 2 | messengre (Messenger) |
| Bit 0 | 1 | whatsapp (WhatsApp) |

### notify_item3
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | TELEGRAM |
| Bit 6 | 64 | Snapchat |
| Bit 5 | 32 | Outlook |
| Bit 4 | 16 | Gmail |
| Bit 3 | 8 | KakaoTalk |
| Bit 2 | 4 | Viber |
| Bit 1 | 2 | Line |
| Bit 0 | 1 | VKontakte |

### notify_item4
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Mormaii Smartwatches |
| Bit 6 | 64 | keep (Keep) |
| Bit 5 | 32 | pinterest_yahoo |
| Bit 4 | 16 | youtube (YouTube) |
| Bit 3 | 8 | tumblr (Tumblr) |
| Bit 2 | 4 | YahooMail |
| Bit 1 | 2 | slack (Slack) |
| Bit 0 | 1 | chatwork (Chatwork) |

### notify_item5
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Flipkart |
| Bit 6 | 64 | Amazon |
| Bit 5 | 32 | Paytm |
| Bit 4 | 16 | Inshorts |
| Bit 3 | 8 | Hotstar |
| Bit 2 | 4 | Dailyhunt |
| Bit 1 | 2 | Redbus |
| Bit 0 | 1 | TikTok (国际版) |

### notify_item6
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Jio_Tv |
| Bit 6 | 64 | Make_My_Trip |
| Bit 5 | 32 | Zomato |
| Bit 4 | 16 | Swiggy |
| Bit 3 | 8 | Phonpe |
| Bit 2 | 4 | Gpay |
| Bit 1 | 2 | Netflix |
| Bit 0 | 1 | Prime |

### notify_item7
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | 事项提醒 |
| Bit 6 | 64 | Ola |
| Bit 5 | 32 | Uber |
| Bit 4 | 16 | YTmusic |
| Bit 3 | 8 | missed_calls |
| Bit 2 | 4 | niosefit |
| Bit 1 | 2 | WhatsApp Business |
| Bit 0 | 1 | Microsoft |

### notify_item8
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Americanas |
| Bit 6 | 64 | Magalu |
| Bit 5 | 32 | Technos Connect |
| Bit 4 | 16 | Mormaii Smartwatch |
| Bit 3 | 8 | 保留/无效 |
| Bit 2 | 4 | 保留/无效 |
| Bit 1 | 2 | Prime vídeo |
| Bit 0 | 1 | Google meet |

### notify_item9
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Rappi |
| Bit 6 | 64 | lfood |
| Bit 5 | 32 | Uber Eats |
| Bit 4 | 16 | 99taxi |
| Bit 3 | 8 | Teams |
| Bit 2 | 4 | Shopee |
| Bit 1 | 2 | Aliexpress |
| Bit 0 | 1 | Enjoei |

### notify_item10
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Caixa economica |
| Bit 6 | 64 | Banco inter |
| Bit 5 | 32 | Correios |
| Bit 4 | 16 | Banco do brasil |
| Bit 3 | 8 | Todoist |
| Bit 2 | 4 | TickTick |
| Bit 1 | 2 | Yahoo |
| Bit 0 | 1 | Mercado livre |

### notify_item11
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | 通用 (General) |
| Bit 6 | 64 | veryfit |
| Bit 5 | 32 | Google Gmail |
| Bit 4 | 16 | 189email |
| Bit 3 | 8 | Exchangeemail |
| Bit 2 | 4 | Zohoemail |
| Bit 1 | 2 | Nhnemail |
| Bit 0 | 1 | Neon |

### notify_item12
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | 今日头条 (Toutiao) |
| Bit 6 | 64 | 支付宝 (Alipay) |
| Bit 5 | 32 | 钉钉 (DingTalk) |
| Bit 4 | 16 | 淘宝 |
| Bit 3 | 8 | Hama Fit Move |
| Bit 2 | 4 | Fastrack Reflex World |
| Bit 1 | 2 | Calendario(谷歌日历) |
| Bit 0 | 1 | alibaba email |

### notify_item13
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | 新浪微博 (国内版) |
| Bit 6 | 64 | 抖音 (国内版) |
| Bit 5 | 32 | 饿了么 (ele.me) |
| Bit 4 | 16 | 美团 (Meituan) |
| Bit 3 | 8 | 百度 (Baidu) |
| Bit 2 | 4 | 拼多多 |
| Bit 1 | 2 | 京东 (JD) |
| Bit 0 | 1 | 天猫 (TMail) |

### notify_item14
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | Itaú |
| Bit 6 | 64 | Bradesco |
| Bit 5 | 32 | Nubank |
| Bit 4 | 16 | Facebook Messenger |
| Bit 3 | 8 | 保留/无效 |
| Bit 2 | 4 | LOOPS FIT |
| Bit 1 | 2 | Ryze Connect |
| Bit 0 | 1 | Titan Smart World |

### notify_item15
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | zoom_workplace (Zoom Workplace) |
| Bit 6 | 64 | didi_taxi (滴滴打车) |
| Bit 5 | 32 | zalo (Zalo) |
| Bit 4 | 16 | health_u (Health &U) |
| Bit 3 | 8 | google_calendar (谷歌日历) |
| Bit 2 | 4 | apple_mail (苹果邮箱) |
| Bit 1 | 2 | apple_calendar (苹果日历) |
| Bit 0 | 1 | google_messages (谷歌地图/谷歌消息) |

### notify_item16
| Bit 位 | 十进制权重 | 对应应用 |
| :---: | :---: | :--- |
| Bit 7 | 128 | 保留/无效 |
| Bit 6 | 64 | 保留/无效 |
| Bit 5 | 32 | 保留/无效 |
| Bit 4 | 16 | 保留/无效 |
| Bit 3 | 8 | 保留/无效 |
| Bit 2 | 4 | 保留/无效 |
| Bit 1 | 2 | 保留/无效 |
| Bit 0 | 1 | buzud (BUZUD) |

---

## 三、 示例与换算方式

如果我们需要开启某个应用通知开关，只需通过按位或将其对应的十进制权重相加。

### 示例 1：设置 `notify_item1` 
如果我们需要开启 **短信 (message)** 和 **微信 (wechat)**：
- 短信位于 `notify_item1` 的 **Bit 1** (权重为 2)
- 微信位于 `notify_item1` 的 **Bit 3** (权重为 8)
- 开启后的十进制值：`2 + 8 = 10`
- 写入 JSON 字段：`"notify_item1": 10`

### 示例 2：设置 `notify_item13`
如果我们需要开启 **天猫 (TMail)** 和 **新浪微博 (国内版)**：
- 天猫位于 `notify_item13` 的 **Bit 0** (权重为 1)
- 新浪微博位于 `notify_item13` 的 **Bit 7** (权重为 128)
- 开启后的十进制值：`1 + 128 = 129`
- 写入 JSON 字段：`"notify_item13": 129`
