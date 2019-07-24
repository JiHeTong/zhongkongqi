# 说明

该文件主要用作打印串口log，接收处理串口命令。

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| uartdebug\_buff\[1024\] | u8 | 串口接收到数据缓冲区 |
| uartdebug\_len | u16 | 串口接收数据长度 |
| uartdebug\_timeout | u16 | 串口接收数据超时 |
| uartdebug\_update\_timeout | u16 | 串口更新超时 |
| enter\_update\_flag | u8 | 更新标志， 1代表升级 |
| voice\_or\_code | u8 | 更新类型，0 代表更新中控器 1代表更新检测板 |
| logo\_flag | u8 | 日志标志 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| blue\_mac\_data | uint8\_t | 蓝牙mac地址 | driver\_bluetooth.c |
| dce\_sim\_ccid\[\] | uinit8\_t | sim卡ccid | driver\_comm.c |
| default\_ip\[4\] | u8 | 默认服务器ip地址 | driver\_upgrade.c |
| default\_port | u16 | 默认服务器端口号 | driver\_upgrade.c |
| default\_apn | u8\* | 默认服务器apn | driver\_upgrade.c |

---

# 宏定义常量

**说明：以下变量都是16进制u8类型**

| 变量名 | 说明 |
| :--- | :--- |
| UART\_CMD\_REQUEST\_DATA | 请求数据命令 |
| UART\_CMD\_SEND\_SUMMER | 发送文件信息 |
| UART\_CMD\_EOT | 结束指令 |
| UART\_CMD\_NAK | 错误应答 |
| UART\_CMD\_ACK | 正确应答 |
| UART\_CMD\_GET\_INFO | 参数查询 |
| UART\_CMD\_GET\_INFO\_ACK | 参数查询回应 |
| UART\_CMD\_SET\_PARA | 设置参数命令 |
| UART\_CMD\_FLASH\_START\_UPDATA | flash开始烧写指令 |
| UART\_CMD\_FLASH\_FINISH\_UPDATE | flash完成烧写指令 |
| UART\_CMD\_FLASH\_DOWN\_UPDATE | flash下载指令 |
| UART\_ERROR\_HEAD | 前导码错误 |
| UART\_ERROR\_SUMMER | 校验和错误 |
| UART\_ERROR\_LEN | 长度错误 |
| UART\_ERROR\_CMD | 不支持的命令码 |
| UART\_ERROR\_SUB\_CMD | 不支持的扩展命令码 |
| UART\_ERROR\_ADDR | 地址错误 |
| UART\_ERROR\_OTHER | 其他错误 |
| UART\_ERROR\_FIEL\_ERROR | 文件写入校验和错误 |

---

# 外部函数

延时，单位毫秒

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

串口升级，成功返回1，失败返回0

```c
uint8_t save_uart_update_data(u8 start_f,u8 *data,u16 len);
```

| start\_f | 升级标志，0是开始是升级，1是保存升级包，2是升级结束 |
| :--- | :--- |
| \*data | 升级数据 |
| len | 数据长度 |

所属文件：driver\_upgrade.c

---

读取网络状态，返回状态信息

```c
u8 read_net_status(void);
```

所属文件：driver\_gprs.c

---

# 内部函数

比较两个字符串是否相等，相等返回1，不相等返回0

```c
 int strstr1(const void *s1, const void *s2)
```

---

将数字转换成16进制

```c
uint8_t tohex(uint8_t b)
```

---

将ascii码转换成16进制

```c
void AsciiStrToBcd(uint8_t *outbuf,uint8_t *b,uint8_t len)
```

| 变量名 | 说明 |
| :--- | :--- |
| \*outbuf | 输出后的16进制字符串 |
| \*b | ascii码 |
| len | ascii码长度 |

---

将字符串转换成信号

```c
void set_signel_data(u8 *data)
```

---

uartdebug串口接收超时

```c
void dec_uartdebug_timeout(void)
```

---

接收uartdebug串口到的字符，拼接成字符串

```c
void dec_uartdebug_rece_data(u8 ch)
```

---

检验串口升级或解析串口命令

```c
void check_enter_update(void)
```

---

恢复出厂模式，参数传1即可，其他无效

```c
void restore_factory(u8 all)
```

---

向串口发送数据

```c
void uart3_send_str(u8 *str)
```

---

打印字符串log

```c
void print_logo_str(u8 logo_s,u8 *str)
```

打印字符串log

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| str | 打印的字符串 |

---

打印log

```c
void print_logo(u8 logo_s,u8 *remind,u8 *data,u16 len,u8 logo_type)
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| remind | log的标题名称 |
| data | 打印的log数据 |
| len | log数据长度 |
| logo\_type | log的数据形式，比如16进制、时间等等。 |

---

打印阈值log

```c
void print_angle_logo(u8 logo_s,u8 *remind,short data)
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| remind | log标题名称 |
| data | log数据 |

---

将字符串里的小写字母转换成大写

```c
void shift_to_upchar(u8 *data,u16 len)
```

| 变量名 | 说明 |
| :--- | :--- |
| data | 要转换的字符串 |
| len | 字符串的长度 |

---

打印所有信息的log

```c
void print_logo_para(void)
```

---

处理串口指令

```c
void proc_uart_at_cmd(u8 *data,u8 len)
```

---



