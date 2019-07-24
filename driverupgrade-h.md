# 宏定义常量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| FLASH\_ONE\_PAGE\_SIZE | u8\(hex\) | 每页的数据尺寸（512字节） |
| FLASH\_PAGE\_SIZE | u8\(hex\) | 页数 |
| FLASH\_START\_ADDR | u8\(hex\) | 参数存放地址 |
| SETUP\_DATA\_START\_ADDR | u8\(hex\) | 内部flash存储数据起始地址 |
| FLASH\_UPDATE\_BUFFER\_START\_ADDR | u8\(hex\) | 程序缓存起始地址,存放在外部flash |
| FLASH\_UPDATE\_START\_ADDR | u8\(hex\) | FLASH烧写起始地址 |
| FLASH\_BACKUPS\_PARA\_ADDR | u8\(hex\) | FLASH备份数据 |
| FLASH\_BACKUPS\_PARA\_SUMER\_NUM | u8\(hex\) | 校验码从IP地址到拥有线路条数的202byte |
| IIC\_LINE\_NUM | u8 | 检测板数量 |
| MAX\_LINE\_NUM | u8 | 检测板最大数量 |
| LINE\_ID\_LEN | u8 | 检测板id长度 |
| LINE\_STATUS\_LEN | u8 | 检测板状态信息长度 |
| LINE\_DATA\_SAVE\_FLASH\_ADDR | u8\(hex\) | 检测板数据存放地址 |
| LINE\_DATA\_SAVE\_FLASH\_LEN | u8\(hex\) | 检测板数据长度 |
| DATA\_SAVE\_NUM | u8 | 保存数据条数 |
| GPRS\_ENVI\_DATA\_SAVE\_FLASH\_ADDR | u8\(hex\) | 自检环境数据存放地址 |

---

# 结构体

系统参数

SYSTEM\_PARA

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| update\_flag\[4\] | u8 | 升级标志 |
| soft\_ver\[16\] | u8 | 软件版本号 |
| check\_sumer\[2\] | u8 | 文件校验和 |
| pro\_file\_len\[3\] | u8 | 文件长度 |
| server\_ip\[4\] | u8 | 服务器ip地址 |
| server\_port | u16 | 服务器端口 |
| server\_ip\_standby\[4\] | u8 | 备用服务器ip地址 |
| server\_port\_standby | u16 | 备用服务器端口 |
| server\_apn\[32\] | u8 | 服务器APN |
| heart\_beat\_time | u16 | 心跳包间隔时间 |
| sms\_center\_num\[24\] | u8 | 短信中心号码 |
| server\_domain\_name\[64\] | u8 | 域名地址 |
| domain\_port | u16 | 域名端口 |
| term\_id\[8\] | u8 | 终端id |
| auto\_check\_time | u16 | 自检时间 |
| timing\_upload\_time | u16 | 定时上报时间 |
| fault\_check\_time | u16 | 门锁开关异常检测时间 |
| sleep\_time | u16 | 休眠时间 |
| line\_check\_time | u16 | 线路板检测时间 |
| ble\_mac\_addr\[16\] | u8 | Bluetooth MAC地址 |
| ble\_broadcast\_uuid\[24\] | u8 | Bluetooth广播名称 |
| temp\_lower\_value | s16 | 低温温度阈值 |
| temp\_upper\_value | s16 | 高温温度阈值 |
| angle\_value | s16 | 倾斜角度阈值 |
| batt\_value | u16 | 电池电量阈值 |
| term\_status | u8 | 终端状态，0 - 正常工作，1-测试状态，2 - 装车运输状态 |
| sumer | u16 | 结构体校验码 |

检测板参数信息

TERM\_LINE\_LIST

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| line\_num | u8 | 检测板数量 |
| line\_addr\[\] | u8 | 检测板地址 |
| line\_id\[\]\[\] | u8 | 检测板id |
| line\_status\[\]\[\] | u8 | 检测板状态 |

---

# 函数声明

向内部flash区写入数据

```c
void WriteFlash(u16 len,u32 *data,u16 addr_start);
```

| 变量名 | 说明 |
| :--- | :--- |
| len | 数据长度 |
| data | 数据 |
| addr\_start | 写入数据的地址 |

---

读取内部flash区数据

```c
u16 ReadFlash(u16 len,u8 *outdata,u16 addr_start);
```

| 变量名 | 说明 |
| :--- | :--- |
| len | 读取的数据长度 |
| outdata | 读取的数据缓冲区 |
| addr\_start | 读取数据的地址 |

---

gsm模块升级，成功返回1，失败返回0

```c
uint8_t save_update_data_handle(u8 command,u8* data,u16 len);
```

| 变量名 | 说明 |
| :--- | :--- |
| command | 指令 |
| data | 数据缓冲区 |
| len | 数据长度 |

---

串口升级

```c
uint8_t save_uart_update_data(u8 start_f,u8 *data,u16 len);
```

| 变量名 | 说明 |
| :--- | :--- |
| start\_f | 指令 |
| data | 数据缓冲区 |
| len | 数据长度 |

---

flash烧写

```c
uint8_t save_uart_upflash_data(u8 start_f,u8 *data,u16 len);    //flash烧写
```

| 变量名 | 说明 |
| :--- | :--- |
| start\_f | 指令 |
| data | 数据缓冲区 |
| len | 数据长度 |

---

保存系统信息参数，mode为模式类型

```c
void flash_write_setup(uint8_t mode)
```

---

读取检测板数据

```c
void flash_read_line_data(void);
```

---

保存检测板信息

```c
void flash_write_line_data(void);
```

---

从flash区读取设备参数

```c
void setup_init(void);
```

---



