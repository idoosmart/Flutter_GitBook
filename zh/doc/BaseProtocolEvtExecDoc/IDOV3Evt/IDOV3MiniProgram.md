### v3设置获取小程序信息


功能表:support_control_mini_program

**1）app发送**

```c
#define MAX_MINI_PROGRAM_NAME_SIZE (30)
// 头部定义
typedef struct protocol_v3_base
{
	uint32_t fixed;
	uint8_t version;
	uint16_t length;
	uint16_t cmd_id; 
	uint16_t nseq;
}protocol_v3_base_s;

struct protocol_v3_set_get_mini_program_info
{
   uint8_t verison; //协议版本号
   uint8_t operate; //0:无效 1:启动小程序 2:删除小程序 3:获取已安装的小程序列表
   uint8_t name_len;//小程序名称长度 最大默认30个字节，包含一个结束符 operate=0 & operate=3无效,获取操作不需要下发名称
 	 char *mini_program_name;//小程序名称 最大默认30个字节，包含一个结束符 operate=0 & operate=3无效,获取操作不需要下发名称
}
```

**2.2 ）ble回复struct protocol_v3_set_get_mini_program_info_reply **：

```c
#define MAX_MINI_PROGRAM_NAME_SIZE (30)
#define MAX_MINI_PROGRAM_NUM       (20)
struct protocol_v3_get_mini_program_info_head
{
   uint8_t mini_program_num;//小程序个数
   uint32_t total_space;    //总空间 单位BYTE
   uint32_t residual_space; //剩余空间 单位BYTE
   uint8_t support_get_mini_program_max_num; //支持获取小程序的最大个数，默认是20个
   uint8_t support_mini_program_name_max_len;//支持的小程序名称最大长度，默认是30个字节，包含一个结束符
   uint8_t data[10];        //预留
}

struct protocol_v3_get_mini_program_info
{
  //最多支持4级，从高位到低位第一个非0的位做第一级版本号 例0x00010203->1.2.3
	 uint32_t mini_program_version;  //版本号
   uint32_t mini_program_size;     //大小
   uint8_t name_len;               //小程序名称长度 最大默认30个字节，包含一个结束符
   char *mini_program_name;        //小程序名称 最大默认30个字节，包含一个结束符
}

struct protocol_v3_set_get_mini_program_info_reply
{
   uint8_t verison;   //协议版本号
   uint8_t operate;   //0:无效 1:启动小程序 2:删除小程序 3:获取已安装的小程序列表
	 uint8_t error_code;
   /* 错误码：
		0:成功
    1:低电
	  2:省电模式中
	  3:充电中
	  4:通话中
	  5:运动中
	  6:当前应用开启中
   */
   struct protocol_v3_get_mini_program_info_head head; //operate=3有效
   struct protocol_v3_get_mini_program_info *info_item;//operate=3有效
}
```
