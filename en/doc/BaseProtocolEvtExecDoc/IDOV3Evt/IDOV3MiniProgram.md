V3 Set Obtaining Applet Information

Function table: support_control_mini_program

**1）app sending **

```c
#define MAX_MINI_PROGRAM_NAME_SIZE (30)
// Header definition
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
   uint8_t verison; //Protocol version number
   uint8_t operate; //0: invalid 1: Start the applet 2: Delete the applet 3: Get the list of installed applet
   uint8_t name_len;//The name of the applet contains a maximum of 30 bytes by default and contains one 														//terminator operate=0 & operate=3. The operation is invalid
 	 char *mini_program_name;//The default name of the applet contains a maximum of 30 bytes and one terminator 														 //operate=0 & operate=3 is invalid. No name is required to obtain the operation
}
```

**2）ble recover struct protocol_v3_set_get_mini_program_info_reply**:

```c
#define MAX_MINI_PROGRAM_NAME_SIZE (30)
#define MAX_MINI_PROGRAM_NUM       (20)
struct protocol_v3_get_mini_program_info_head
{
   uint8_t mini_program_num;//Number of small programs
   uint32_t total_space;    //Total space unit：BYTE
   uint32_t residual_space; //Residual space unit：BYTE
   uint8_t support_get_mini_program_max_num; //The maximum number of small programs supported. The default is 20
   uint8_t support_mini_program_name_max_len;//The maximum length of the supported applet name is 30 bytes by 																							 //default and contains a terminator
   uint8_t data[10];        //reserve
}

struct protocol_v3_get_mini_program_info
{
  //A maximum of four levels are supported, with the first non-0 bit being the first-level version number from 		//high to low    example：0x00010203->1.2.3
	 uint32_t mini_program_version;  //Version number
   uint32_t mini_program_size;     //size
   uint8_t name_len;               //The maximum default length of a small program name is 30 bytes and contains 																		//a terminator
   char *mini_program_name;        //The small program name defaults to a maximum of 30 bytes and contains a 																			 //terminator
}

struct protocol_v3_set_get_mini_program_info_reply
{
   uint8_t verison;   //Version number
   uint8_t operate;   //0: invalid 1: Start the applet 2: Delete the applet 3: Get the list of installed applet
	 uint8_t error_code;
   /* 错误码：
		0: success
		1: Low power
		2: Power saving mode
		3: Charging
		4: The call is ongoing
		5: In motion
		6: The application is being started
   */
   struct protocol_v3_get_mini_program_info_head head; //operate=3
   struct protocol_v3_get_mini_program_info *info_item;//operate=3有效
}
```
