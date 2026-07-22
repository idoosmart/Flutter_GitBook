
**`备注：android只用到了来电开关 'call_switch'`**

| 1Byte                                                        | 1Byte                                                        | 1Byte                                                        |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| notify_switch<br />配对状态<br />0x55：手表配对开<br />0xAA：手表配对关<br />~~0x88：设置子开关(预留)(废弃)~~<br />~~0xBB：只开bt（开关）(废弃)~~<br />~~0xCC：ble、bt都开（开关）(废弃)~~ | notify_item1<br />app开关子项1<br />[跳转到位置](#notifyitem1) | notify_item2<br />app开关子项2<br />[跳转到位置](#notifyitem2) |
| **1Byte**                                                    | **1Byte**                                                    | **1Byte**                                                    |
| call_switch<br />来电子提醒开关<br />0x55：开，0xAA：关，0x00:无效 | call_delay<br />来电提醒延时<br />单位s                      | notify_item3<br />app开关子项3<br />[跳转到位置](#notifyitem3) |
| **1Byte**                                                    | **1Byte**                                                    | **1Byte**                                                    |
| notify_item4<br />app开关子项4<br />[跳转到位置](#notifyitem4) | notify_item5<br />app开关子项5<br />[跳转到位置](#notifyitem5) | notify_item6 <br />app开关子项6<br />[跳转到位置](#notifyitem6) |
| **1Byte**                                                    | **1Bytes**                                                   | **1Bytes**                                                   |
| notify_item7<br />app开关子项7<br />[跳转到位置](#notifyitem7) | notify_item8<br />app开关子项8<br />[跳转到位置](#notifyitem8) | notify_item9<br />app开关子项9<br />[跳转到位置](#notifyitem9) |
| **1Byte**                                                    | **1Byte**                                                    | **1Byte**                                                    |
| notify_item10<br />app开关子项10<br />[跳转到位置](#notifyitem10) | 子消息总开关<br />功能开启有效<br />0x55开 0xAA关            | notify_item11<br />app开关子项11<br />[跳转到位置](#notifyitem11) |
| **1Byte**                                                    | **1Byte**                                                    | **1Byte**                                                    |
| notify_item12<br />app开关子项12<br />[跳转到位置](#notifyitem12) | notify_item13<br />app开关子项13<br />[跳转到位置](#notifyitem13) | notify_item14<br />app开关子项14<br />[跳转到位置](#notifyitem14) |

***说明：**

```c
- 通知提醒开关0x55：总开关开， 0xAA:总开关关， 0x88：设置子开关，0x00：无效）
- 提醒项子开关1，提醒项子开关2
- 来电子开关（0x55：开，0xAA：关，0x00:无效）
- 来电延时（单位：s）   提醒项子开关3   （预留）全部补0

- bit位说明：0x00：表示关，0x01：表示开
```



<span id=notifyitem1>**notify_item1**</span>

| bit  | 字段名   | 说明     | 
| ---- | -------- | -------- | 
| 0    |          | 无效     | 
| 1    | message  | 短信     |
| 2    | email    | 邮件     | 
| 3    | wechat   | 微信     | 
| 4    | qq       | QQ       | 
| 5    | weibo    | 微博     | 
| 6    | facebook | facebook | [跳转到位置](#jump0) |
| 7    | twitter  | twitter  | [跳转到位置](#jump0) |

<span id=notifyitem2>**notify_item2 **</span>

| bit  | 字段名     | 说明      | 支持该应用的功能表   |
| ---- | ---------- | --------- | -------------------- |
| 0    | whatsapp   | WhatsApp  | [跳转到位置](#jump1) |
| 1    | messengre  | Messenger | [跳转到位置](#jump1) |
| 2    | instagram  | Instagram | [跳转到位置](#jump1) |
| 3    | linked_in  | Linked in | [跳转到位置](#jump1) |
| 4    | calendar   | 日历事件  | [跳转到位置](#jump1) |
| 5    | skype      | Skype     | [跳转到位置](#jump1) |
| 6    | alarmClock | 闹钟事件  | [跳转到位置](#jump1) |
| 7    | other      | other     | [跳转到位置](#jump1) |

<span id=notifyitem3>**notify_item3**</span>

| bit  | 说明      | 支持该应用的功能表   |
| ---- | --------- | -------------------- |
| 0    | VKontakte | [跳转到位置](#jump2) |
| 1    | Line      | [跳转到位置](#jump2) |
| 2    | Viber     | [跳转到位置](#jump2) |
| 3    | KakaoTalk | [跳转到位置](#jump2) |
| 4    | Gmail     | [跳转到位置](#jump2) |
| 5    | Outlook   | [跳转到位置](#jump2) |
| 6    | Snapchat  | [跳转到位置](#jump2) |
| 7    | TELEGRAM  | [跳转到位置](#jump2) |

<span id=notifyitem4>**notify_item4**</span>

| bit  | 说明                 | 支持该应用的功能表      |
| ---- | -------------------- | ----------------------- |
| 0    | chatwork             | [跳转到位置](#jump1)    |
| 1    | slack                | 0x21   | [跳转到位置](#jump1)    |
| 2    | YahooMail            | 0x22   | [跳转到位置](#jump1)    |
| 3    | tumblr               | 0x23   | [跳转到位置](#jump1)    |
| 4    | youtube              | 0x24   | [跳转到位置](#jump1)    |
| 5    | pinterest_yahoo      | 0x25   | [跳转到位置](#jump1)    |
| 6    | keep                 | 0x36   | [跳转到位置](#jump1)    |
| 7    | Mormaii Smartwatches | 0x76   | [跳转到位置](#v3data52) |

<span id=notifyitem5>**notify_item5**</span>

| bit  | 说明      | 索引值 | 支持该应用的功能表   |
| ---- | --------- | ------ | -------------------- |
| 0    | TikTok    | 0x26   | [跳转到位置](#jump4) |
| 1    | Redbus    | 0x27   | [跳转到位置](#jump4) |
| 2    | Dailyhunt | 0x28   | [跳转到位置](#jump4) |
| 3    | Hotstar   | 0x29   | [跳转到位置](#jump4) |
| 4    | Inshorts  | 0x2A   | [跳转到位置](#jump4) |
| 5    | Paytm     | 0x2B   | [跳转到位置](#jump4) |
| 6    | Amazon    | 0x2C   | [跳转到位置](#jump4) |
| 7    | Flipkart  | 0x2D   | [跳转到位置](#jump4) |

<span id=notifyitem6>**notify_item6**</span>

| bit  | 说明         | 索引值 | 支持该应用的功能表   |
| ---- | ------------ | ------ | -------------------- |
| 0    | Prime        | 0x2E   | [跳转到位置](#jump5) |
| 1    | Netflix      | 0x2F   | [跳转到位置](#jump5) |
| 2    | Gpay         | 0x30   | [跳转到位置](#jump5) |
| 3    | Phonpe       | 0x31   | [跳转到位置](#jump5) |
| 4    | Swiggy       | 0x32   | [跳转到位置](#jump5) |
| 5    | Zomato       | 0x33   | [跳转到位置](#jump5) |
| 6    | Make_My_Trip | 0x34   | [跳转到位置](#jump5) |
| 7    | Jio_Tv       | 0x35   | [跳转到位置](#jump5) |

<span id=notifyitem7>**notify_item7**</span>

| bit  | 说明              | 索引值 | 支持该应用的功能表     |
| ---- | ----------------- | ------ | ---------------------- |
| 0    | Microsoft         | 0x37   | [跳转到位置](#v3data2) |
| 1    | WhatsApp Business | 0x38   | [跳转到位置](#v3data2) |
| 2    | niosefit          | 0x39   | [跳转到位置](#v3data2) |
| 3    | missed_calls      | 0x3A   | [跳转到位置](#v3data2) |
| 4    | YTmusic           | 0x3C   | [跳转到位置](#v3data2) |
| 5    | Uber              | 0x3D   | [跳转到位置](#v3data2) |
| 6    | Ola               | 0x3E   | [跳转到位置](#v3data2) |
| 7    | 事项提醒          | 0x3F   | [跳转到位置](#v3data2) |

<span id=notifyitem8>**notify_item8**</span>

| bit  | 说明               | 索引值 | 支持该应用的功能表      |
| ---- | ------------------ | ------ | ----------------------- |
| 0    | Google meet        | 0x40   | [跳转到位置](#v3data15) |
| 1    | Prime vídeo        | 0x75   | [跳转到位置](#v3data52) |
| 4    | Mormaii Smartwatch | 0x41   | [跳转到位置](#v3data15) |
| 5    | Technos Connect    | 0x42   | [跳转到位置](#v3data15) |
| 6    | Magalu             | 0x43   | [跳转到位置](#v3data15) |
| 7    | Americanas         | 0x44   | [跳转到位置](#v3data15) |

<span id=notifyitem9>**notify_item9**</span>

| bit  | 说明       | 索引值 | 支持该应用的功能表      |
| ---- | ---------- | ------ | ----------------------- |
| 0    | Enjoei     | 0x45   | [跳转到位置](#v3data20) |
| 1    | Aliexpress | 0x46   | [跳转到位置](#v3data20) |
| 2    | Shopee     | 0x47   | [跳转到位置](#v3data20) |
| 3    | Teams      | 0x48   | [跳转到位置](#v3data20) |
| 4    | 99taxi     | 0x49   | [跳转到位置](#v3data20) |
| 5    | Uber Eats  | 0x4A   | [跳转到位置](#v3data20) |
| 6    | lfood      | 0x4B   | [跳转到位置](#v3data20) |
| 7    | Rappi      | 0x4C   | [跳转到位置](#v3data20) |

<span id=notifyitem10>**notify_item10**</span>

| bit  | 说明            | 索引值 | 支持该应用的功能表      |
| ---- | --------------- | ------ | ----------------------- |
| 0    | Mercado livre   | 0x4D   | [跳转到位置](#v3data21) |
| 1    | Yahoo           | 0x4E   | [跳转到位置](#v3data21) |
| 2    | TickTick        | 0x73   | [跳转到位置](#v3data51) |
| 3    | Todoist         | 0x74   | [跳转到位置](#v3data51) |
| 4    | Banco do brasil | 0x69   | [跳转到位置](#v3data42) |
| 5    | Correios        | 0x6A   | [跳转到位置](#v3data42) |
| 6    | Banco inter     | 0x6B   | [跳转到位置](#v3data42) |
| 7    | Caixa economica | 0x6C   | [跳转到位置](#v3data42) |

<span id=setnotifyitem11>**notify_item11**</span>

| bit  | 说明            | 索引值 | 支持该应用的功能表      |
| ---- | --------------- | ------ | ----------------------- |
| 0    | Neon            | 0x6D   | [跳转到位置](#v3data51) |
| 1    | Santander       | 0x6E   | [跳转到位置](#v3data51) |
| 2    | Next            | 0x6F   | [跳转到位置](#v3data51) |
| 3    | Shein           | 0x70   | [跳转到位置](#v3data51) |
| 4    | Google task     | 0x71   | [跳转到位置](#v3data51) |
| 5    | Microsoft to do | 0x72   | [跳转到位置](#v3data51) |
| 6    | veryfit         | 0x4F   | [跳转到位置](#v3data25) |
| 7    | 通用            | 0x50   | [跳转到位置](#v3data25) |

<span id=setnotifyitem12>**notify_item12**</span>

| bit  | 说明                  | 索引值 | 支持该应用的功能表       |
| ---- | --------------------- | ------ | ------------------------ |
| 0    | alibaba email         | 0x51   | [跳转到位置](#v3data30)  |
| 1    | Calendario(谷歌日历)  | 0x52   | [跳转到位置](#v3data30)  |
| 2    | Fastrack Reflex World | 0x53   | [跳转到位置](#v3data30)  |
| 3    | Hama Fit Move         | 0x54   | [跳转到位置](#v3data30)  |
| 4    | 淘宝                  | 0x55   | [跳转到位置](#v3data30)  |
| 5    | 钉钉(DingTalk)        | 0x56   | [跳转到位置](#v3d6ata30) |
| 6    | 支付宝(Alipay)        | 0x57   | [跳转到位置](#v3data30)  |
| 7    | 今日头条(Toutiao)     | 0x58   | [跳转到位置](#v3data30)  |

<span id=setnotifyitem13>**notify_item13**</span>

| bit  | 说明             | 索引值 | 支持该应用的功能表      |
| ---- | ---------------- | ------ | ----------------------- |
| 0    | 天猫(TMail)      | 0x59   | [跳转到位置](#v3data37) |
| 1    | 京东(JD)         | 0x5A   | [跳转到位置](#v3data37) |
| 2    | 拼多多           | 0x5B   | [跳转到位置](#v3data37) |
| 3    | 百度(Baidu)      | 0x5C   | [跳转到位置](#v3data37) |
| 4    | 美团(Meituan)    | 0x5D   | [跳转到位置](#v3data37) |
| 5    | 饿了么(ele.me)   | 0x5E   | [跳转到位置](#v3data37) |
| 6    | 抖音(国内版)     | 0x5F   | [跳转到位置](#v3data37) |
| 7    | 新浪微博(国内版) | 0x60   | [跳转到位置](#v3data37) |

<span id=setnotifyitem14>**notify_item14**</span>

| bit  | 说明               | 索引值 | 支持该应用的功能表      |
| ---- | ------------------ | ------ | ----------------------- |
| 0    | Titan Smart World  | 0x61   | [跳转到位置](#v3data40) |
| 1    | Ryze Connect       | 0x62   | [跳转到位置](#v3data42) |
| 2    | LOOPS FIT          | 0x63   | [跳转到位置](#v3data42) |
| 3    |                    |        |                         |
| 4    | Facebook Messenger | 0x65   | [跳转到位置](#v3data52) |
| 5    | Nubank             | 0x66   | [跳转到位置](#v3data52) |
| 6    | Bradesco           | 0x67   | [跳转到位置](#v3data52) |
| 7    | Itaú               | 0x68   | [跳转到位置](#v3data42) |
