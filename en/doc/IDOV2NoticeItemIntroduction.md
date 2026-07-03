# IDO Notification Center switch notify_item Bit Definition Description

When setting or obtaining the state of the notification center, each field from `notify_item1` to `notify_item16` represents an 8-bit byte (represented as an integer from 0 to 255 in JSON transmission).

According to the authoritative definition of the **C-Lib Protocol Specification and Protocol Documents**, all `notify_item` switches are **forward bit mapped** (where Bit 0 corresponds to the low-bit binary `1 shl 0` and Bit 7 corresponds to the high-bit binary `1 shl 7`).

> [!NOTE]
> - **Switch Value**: `0` means Off, `1` means On.
> - **C-Lib V3 Protocol Naming Correspondence**: In the underlying C-language V3 message notification protocol (command ID `0x33`), the `notify_item1` (corresponding to google_messages, etc.) and `notify_item2` (corresponding to buzud) of the `protocol_v3_msg_notify_remind_data_decode_reply` struct are mapped directly to `notify_item15` and `notify_item16` respectively in the JSON interface exposed by the SDK to Flutter.

---

## 1. Decimal Weights for notify_item 1 ~ 16

In these fields, the decimal weights of the bits are as follows (consistent with standard bitwise operation habits):
- **Bit 7** = 0x80 (128)
- **Bit 6** = 0x40 (64)
- **Bit 5** = 0x20 (32)
- **Bit 4** = 0x10 (16)
- **Bit 3** = 0x08 (8)
- **Bit 2** = 0x04 (4)
- **Bit 1** = 0x02 (2)
- **Bit 0** = 0x01 (1)

---

## 2. Detailed Bit Mapping List

### notify_item1
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | twitter (Twitter) |
| Bit 6 | 64 | facebook (Facebook) |
| Bit 5 | 32 | weibo (Weibo) |
| Bit 4 | 16 | qq (QQ) |
| Bit 3 | 8 | wechat (WeChat) |
| Bit 2 | 4 | email (Email) |
| Bit 1 | 2 | message (SMS) |
| Bit 0 | 1 | Reserved/Invalid |

### notify_item2
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | other (Other) |
| Bit 6 | 64 | alarmClock (Alarm Events) |
| Bit 5 | 32 | skype (Skype) |
| Bit 4 | 16 | calendar (Calendar Events) |
| Bit 3 | 8 | linked_in (LinkedIn) |
| Bit 2 | 4 | instagram (Instagram) |
| Bit 1 | 2 | messengre (Messenger) |
| Bit 0 | 1 | whatsapp (WhatsApp) |

### notify_item3
| Bit | Decimal Weight | Corresponding App |
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
| Bit | Decimal Weight | Corresponding App |
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
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Flipkart |
| Bit 6 | 64 | Amazon |
| Bit 5 | 32 | Paytm |
| Bit 4 | 16 | Inshorts |
| Bit 3 | 8 | Hotstar |
| Bit 2 | 4 | Dailyhunt |
| Bit 1 | 2 | Redbus |
| Bit 0 | 1 | TikTok |

### notify_item6
| Bit | Decimal Weight | Corresponding App |
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
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Matters Remind |
| Bit 6 | 64 | Ola |
| Bit 5 | 32 | Uber |
| Bit 4 | 16 | YTmusic |
| Bit 3 | 8 | missed_calls |
| Bit 2 | 4 | niosefit |
| Bit 1 | 2 | WhatsApp Business |
| Bit 0 | 1 | Microsoft |

### notify_item8
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Americanas |
| Bit 6 | 64 | Magalu |
| Bit 5 | 32 | Technos Connect |
| Bit 4 | 16 | Mormaii Smartwatch |
| Bit 3 | 8 | Reserved/Invalid |
| Bit 2 | 4 | Reserved/Invalid |
| Bit 1 | 2 | Prime vídeo |
| Bit 0 | 1 | Google meet |

### notify_item9
| Bit | Decimal Weight | Corresponding App |
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
| Bit | Decimal Weight | Corresponding App |
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
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | General |
| Bit 6 | 64 | veryfit |
| Bit 5 | 32 | Google Gmail |
| Bit 4 | 16 | 189email |
| Bit 3 | 8 | Exchangeemail |
| Bit 2 | 4 | Zohoemail |
| Bit 1 | 2 | Nhnemail |
| Bit 0 | 1 | Neon |

### notify_item12
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Toutiao |
| Bit 6 | 64 | Alipay |
| Bit 5 | 32 | DingTalk |
| Bit 4 | 16 | Taobao |
| Bit 3 | 8 | Hama Fit Move |
| Bit 2 | 4 | Fastrack Reflex World |
| Bit 1 | 2 | Calendario |
| Bit 0 | 1 | alibaba email |

### notify_item13
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Weibo (Domestic) |
| Bit 6 | 64 | Douyin (Domestic) |
| Bit 5 | 32 | ele.me |
| Bit 4 | 16 | Meituan |
| Bit 3 | 8 | Baidu |
| Bit 2 | 4 | Pinduoduo |
| Bit 1 | 2 | JD |
| Bit 0 | 1 | TMail |

### notify_item14
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Itaú |
| Bit 6 | 64 | Bradesco |
| Bit 5 | 32 | Nubank |
| Bit 4 | 16 | Facebook Messenger |
| Bit 3 | 8 | Reserved/Invalid |
| Bit 2 | 4 | LOOPS FIT |
| Bit 1 | 2 | Ryze Connect |
| Bit 0 | 1 | Titan Smart World |

### notify_item15
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | zoom_workplace (Zoom Workplace) |
| Bit 6 | 64 | didi_taxi (Didi Taxi) |
| Bit 5 | 32 | zalo (Zalo) |
| Bit 4 | 16 | health_u (Health &U) |
| Bit 3 | 8 | google_calendar (Google Calendar) |
| Bit 2 | 4 | apple_mail (Apple Mail) |
| Bit 1 | 2 | apple_calendar (Apple Calendar) |
| Bit 0 | 1 | google_messages (Google Messages) |

### notify_item16
| Bit | Decimal Weight | Corresponding App |
| :---: | :---: | :--- |
| Bit 7 | 128 | Reserved/Invalid |
| Bit 6 | 64 | Reserved/Invalid |
| Bit 5 | 32 | Reserved/Invalid |
| Bit 4 | 16 | Reserved/Invalid |
| Bit 3 | 8 | Reserved/Invalid |
| Bit 2 | 4 | Reserved/Invalid |
| Bit 1 | 2 | Reserved/Invalid |
| Bit 0 | 1 | buzud (BUZUD) |

---

## 3. Example and Conversion Method

To enable a notification switch for an app, simply add up the decimal weights of the corresponding bits.

### Example 1: Set `notify_item1`
If we need to enable **SMS (message)** and **WeChat (wechat)**:
- SMS is located at **Bit 1** of `notify_item1` (weight 2)
- WeChat is located at **Bit 3** of `notify_item1` (weight 8)
- Combined decimal value: `2 + 8 = 10`
- Set in JSON field: `"notify_item1": 10`

### Example 2: Set `notify_item13`
If we need to enable **TMail** and **Weibo (Domestic)**:
- TMail is located at **Bit 0** of `notify_item13` (weight 1)
- Weibo (Domestic) is located at **Bit 7** of `notify_item13` (weight 128)
- Combined decimal value: `1 + 128 = 129`
- Set in JSON field: `"notify_item13": 129`
