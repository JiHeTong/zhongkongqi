# 说明

该文件主要用作网络操作

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| gprs\_tcp\_sending\_buffer\_command\[\] | uinit8\_t | 发送网络数据缓冲区 |
| gprs\_tcp\_need\_resend\_flag | uint8\_t | 重发送数据标志 |
| Pown\_or\_reset\_flag | uinit8\_t | 重新上电或复位后，登录后上报一次数据 |
| Client\_request\_send\_flag | uint8\_t | 终端请求发送 |
| Client\_enter\_cnt | uint8\_t | 上传登录包次数 |
| Client\_enter\_flag | uint8\_t | 上传登录包标志    0 -- 重启未登录    1 -- 请求登录 2 -- 登录成功或不请求登录 |
| Client\_enter\_timeout | uint8\_t | 登录超时时间 |
| line\_alarm\_cnt | uinit8\_t | 检测板数量 |
| line\_alarm\_num | uinit8\_t | 需要上报的检测板数量 |
| upline\_result\[\] | uinit8\_t | 检测板升级结果 |
| Client\_save\_data\_send\_flag | uinit8\_t | 自检记录数据    1-上报 |
| save\_data\_cnt | uinit8\_t | 保存数据条数 |
| http\_para | HTTP\_PARA（结构体） | HTTP在线升级信息 |
| Client\_request\_get\_url | uint8\_t | 终端请求升级 |
| Tcp\_update\_flag | uint8\_t | 升级标志 |
| Tcp\_update\_timeout | uint16\_t | 升级超时时间 |
| net\_status | u8 | 网络状态 |
| term\_status | u8 | 终端状态 |
| connect\_cmnet\_cnt | u8 | 连接服务端次数 |
| GPRS\_COMMAND\[\] | uint8\_t\* | gprs协议指令 |
| reset\_time\_clear\_flag | uint8\_t | 重置时间清理标志 |
| reset\_timeout | uint16\_t | 重置超时 |
| check\_timing\_upload\_err\_timeout | uint16\_t | 登录失败，重试超时时间 |
| DATA\_PACKET | u16 | 每次写入flash的数据大小 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| work\_status | u16 | 工作状态 | main.c |
| Enter\_sleep\_flag | uint8\_t | 进入休眠标志 | main.c |
| BT\_status\_led | uint8\_t | 蓝牙状态指示灯 | driver\_bluetooth.c |
| dce\_sim\_ccid | uint8\_t | sim卡ccid | driver\_comm.c |
| system\_para | SYSTEM\_PARA（结构体） | 系统信息参数 | driver\_upgrade.c |
| term\_line\_data | TERM\_LINE\_LIST（结构体） | 检测板信息参数 | driver\_upgrade.c |

---

# 外部函数声明

延时毫秒

```c
void delay_ms(u16 ms);
```

所属文件main.c

---

看门狗重置

```c
void SinWatchDog_Reset(void);
```

所属文件：driver\_timer.c

---

设置工作状态

```c
void set_work_status(u16 status);
```

所谓文件：main.c

---

清理工作状态

```c
 void clr_word_status(u8 status);
```

所属文件：main.c

---

打印log

```c
void print_logo(u8 logo_s,u8 *remind,u8 *data,u16 len,u8 logo_type);
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| remind | log的标题名词 |
| data | log数据 |
| len | log的长度 |
| logo\_type | log的数据类型，比如16进制、字符串等等 |

所属文件：dev\_uartlogo.c

---

打印字符串

```c
void print_logo_str(u8 logo_s,u8 *str);
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| str | 字符串 |

所属文件：dev\_uartlogo.c

---

设置休眠等待时间

```c
void set_sleep_wait_timeout(uint16_t time)
```

所属文件：main.c

---

打印温度、电量、角度等信息log

```c
void print_angle_logo(u8 logo_s,u8 *remind,short data)
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| remind | log的标题名称 |
| data | log数据 |

所属文件：dev\_uartlogo.c

---

保存更新包，返回: 0-程序校验错误  1-拷贝数据出错

```c
u8 save_update_data(void);
```

所属文件：driver\_upgrade.c

---

# 内部函数

设置网络状态

```c
void set_net_status(u8 st)
```

---

设置终端状态

```c
void set_term_status(u8 st)
```

---

读取网络状态

```c
u8 read_net_status(void)
```

---

读取终端状态

```c
u8 read_term_status(void)
```

---

要上传的表单，data为上传数据，返回表单

```c
uint8_t *command_form(uint8_t *data)
```

---

向网络模块发送指令

```c
void driver_gprs_usart_send_buffer(uint8_t cmd_index)
```

---

检验重发

```c
void check_gprs_need_resend(void)
```

---

发送网络数据

```c
void driver_gprs_tcp_data_send(uint8_t *ptr, uint16_t len)
```

| 变量名 | 说明 |
| :--- | :--- |
| ptr | 数据 |
| len | 数据长度 |

---

添加检测板状态数据

```c
void driver_add_status_data(uint8_t *check_time,uint8_t *id,uint32_t value_type,uint8_t *value,uint8_t *sendbuff,uint16_t *sendlen)
```

| 变量名 | 说明 |
| :--- | :--- |
| check\_time | 设备当前时间 |
| id | 设备id |
| value\_type | value类型 |
| value | value数据 |
| sendbuff | 发送数据缓冲区 |
| sendlen | 发送数据长度 |

---

上报检测板变化数据

```c
void driver_gprs_line_data_to_server(uint32_t command,uint32_t source)
```

| 变量名 | 说明 |
| :--- | :--- |
| command | 协议指令 |
| source | 资源数据 |

---

处理服务器设置指令

```c
void proc_server_result_seting(uint8_t *data)
```

---

解析从服务端获取的升级数据

```c
uint8_t http_update_data(uint8_t *data)
```

---

接收解析服务端数据

```c
void driver_gprs_usart_rx_from_server(uint8_t *rx_buffer,uint16_t rx_len)
```

| 变量名 | 说明 |
| :--- | :--- |
| rx\_buffer | 接收数据缓冲区 |
| rx\_len | 接收数据长度 |

---

检验重发

```c
uint8_t check_flash_gprs_save_need_send(void)
```

---

拼接http地址

```c
char *GSM_HTTPURL(char *data)
```

---

拼接下载到模块RAM地址

```c
char *GSM_HTTPDL(char *data)
```

---

获取http内容

```c
char *GSM_HTTPGET(u8 mode,char *data)
```

| 变量名 | 说明 |
| :--- | :--- |
| mode | 模式类型 |
| data | 数据缓冲区 |

---

打开文件，timeOut为超时时间

```c
u8 AT_FOPEN(u16 timeOut)
```

---

更新失败则先关闭模块中打开的文件，timeOut超时时间

```c
u8 AT_FCLOSE(u16 timeOut)
```

---

发送http指令

```c
char HTTP_SendCmd(char* cmd, char* result, u16 timeOut)
```

| 变量名 | 说明 |
| :--- | :--- |
| cmd | 发送的指令 |
| result | 回显结果 |
| timeOut | 超时时间 |

---

下载文件

```c
u8 HTTP_DOWNLOAD_FILE(u16 timeOut)
```

---

总体的下载过程

```c
char HTTP_download(void)
```

---

读取模块中下载好的固件包，并写入外部flash，return 0:无数据 1:成功  2:数据错误

```c
u8 READ_GSM_RAM(u8 *outdata,u16 *data_len)
```

| 变量名 | 说明 |
| :--- | :--- |
| outdata | 读取的数据缓冲 |
| data\_len | 读取的数据长度 |

---



