# 说明

该文件主要用于蓝牙方面的相关操作，包括接收\发送蓝牙数据，解析蓝牙数据等等

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| chUartBuf\[\] | uinit8\_t | 蓝牙接收数据缓冲区 |
| chUartBufHead | uint32\_t | 缓冲区字符串索引 |
| chUartBufEnd | uint32\_t | 缓冲区没接收到数据的标志位0 |
| chUartTimeout | uint32\_t | 蓝牙接收数据超时 |
| blue\_mac\_data\[\] | uint8\_t | 蓝牙mac地址 |
| BT\_status\_led | uint8\_t | 蓝牙状态灯 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| system\_para | SYSTEM\_PARA（结构体） | 系统参数信息 | driver\_upgrade.c |
| term\_line\_data | TERM\_LINE\_LIST | 检测板参数信息 | driver\_upgrade.c |
| Enter\_sleep\_flag | uinit8\_t | 休眠标志 | main.c |
| flag\_module\_start | uinit8\_t | 设备启动标志 | driver\_comm.c |

---

# 宏定义常量

**说明：以下变量都是16进制u8类型**

| 变量名 | 说明 |
| :--- | :--- |
| BLUE\_RECE\_PACK\_HEAD | 接收数据头 |
| BLUE\_SEND\_PACK\_HEAD | 发送数据头 |
| BLUE\_PACK\_CRC | 发送数据尾 |
| BLUE\_CMD\_UPLPAD\_LINE\_STATUS | 上报服务器端子状态 |
| BLUE\_CMD\_GET\_LINE\_STATUS | 查询端子占用情况 |
| BLUE\_CMD\_SET\_MAC | 设置mac地址 |
| BLUE\_CMD\_SET\_TEMP\_VALUE | 设置温度阈值 |
| BLUE\_CMD\_SET\_OTHER\_VALUE | 设置其他阈值 |
| BLUE\_CMD\_SET\_IP | 设置ip |
| BLUE\_CMD\_SET\_PORT | 设置端口 |
| BLUE\_CMD\_SET\_NAME | 设置蓝牙名称 |
| BLUE\_CMD\_GET\_MAC | 获取蓝牙mac |
| BLUE\_CMD\_OPEN\_LOCK | 开锁 |
| BLUE\_CMD\_SET\_TIME | 设置时间 |
| BLUE\_CMD\_GET\_PARA | 获取设备参数 |
| BLUE\_CMD\_ADD\_LINE | 绑定检测板 |
| BLUE\_CMD\_DEL\_LINE | 解除检测板 |
| BLUE\_CMD\_RESET\_LINE | 重新检查已绑定在位的检测板 |
| BLUE\_CMD\_SET\_LINESIDE | 设置检测板方向 |
| BLUE\_CMD\_RESET\_CONTROLLER | 复位重启中控 |
| BLUE\_CMD\_GET\_VER | 获取中控版本号和版本日期 |
| BLUE\_CMD\_GET\_NET\_STA | 获取中控版本当前网络状态 |
| BLUE\_CMD\_INIT\_LINE | 恢复检测板 |

---

# 外部函数

微秒延时

```c
void delay_us(u16 us);
```

所属文件：main.c

---

毫秒延时

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

看门狗重置

```c
void SinWatchDog_Reset(void);
```

所属文件：driver\_timer.c

---

设置usb连接标志

```c
void set_usb_connect_flag(u8 flag);
```

所属文件：main.c

---

登陆失败条件启动重发登陆

```c
void check_net_sta_send_data(void)
```

所属文件：driver\_comm.c

---

打印log

```c
void print_logo(u8 logo_s,u8 *remind,u8 *data,u16 len,u8 logo_type);
```

所属文件：dev\_uartlogo.c

---

# 内部函数

蓝牙串口初始化，BR为波特率

```c
void system_sc_uart2_init(u32 BR)
```

---

蓝牙串口中断函数，用来接收数据

```c
void SC2_IRQHandler(void)
```

---

将16进制数据转换成ascii码

```c
u8  hex_to_ascii(u8 hex)
```

---

将ascii码转换成16进制数据

```c
u8  ascii_to_hex(u8 ascii)
```

---

将16进制数据数组转换成ascii数组

```c
void hex_to_hascii(u8 *h_ascii,u8 *hex_data,u8 len)
```

---

添加每个检测板状态

```c
void add_blue_one_line_status(u8 *status,u8 *sendbuff,u16 *sendlen)
```

| 变量名 | 说明 |
| :--- | :--- |
| status | 状态信息 |
| sendbuff | 发送数据的缓冲区 |
| sendlen | 发送数据的长度 |

---

设置温度阈值

```c
void set_temp_value(u8 *data)
```

---

设置其他阈值

```c
void set_value_envi(u8 *data)
```

---

获取参数信息

```c
void get_term_para(u8 *data,u16 *datalen)
```

| 变量名 | 说明 |
| :--- | :--- |
| data | 获取参数的缓冲区 |
| datalen | 参数的长度地址 |

---

获取中控版本号和版本日期，参数同上

```c
void get_term_ver(u8 *data,u16 *datalen)
```

---

蓝牙解锁状态

```c
void blue_unlock_status(u8 lock_type,u8 *sendbuff,u16 *sendlen)
```

| 变量名 | 说明 |
| :--- | :--- |
| lock\_type | 锁类型 |
| sendbuff | 发送数据缓冲区 |
| sendlen | 发送数据长度地址 |

---

向蓝牙设备发送数据

```c
void send_blue_cmd_data(u8 cmd,u8 *data,u16 datalen)
```

| 变量名 | 说明 |
| :--- | :--- |
| cmd | 命令标志 |
| data | 发送的数据 |
| datalen | 数据长度 |

---





