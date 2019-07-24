# 说明

该文件主要用作固件升级操作

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| system\_para | SYSTEM\_PARA（结构体） | 设备参数信息 |
| term\_line\_data | TERM\_LINE\_LIST（结构体） | 检测板参数信息 |
| update\_len | u32 | 更新数据长度 |
| update\_addr | u32 | 更新数据地址 |
| update\_sumer | u16 | 更新数据校验和 |
| default\_ip\[\] | u8 | 默认服务端ip地址 |
| default\_port | u16 | 默认服务端端口号 |
| default\_apn | u8\* | 默认专网方式 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| http\_para | HTTP\_PARA（结构体） | http协议传输参数 | driver\_gprs.c |

---

# 外部函数

延时毫秒

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

指定地址多个块擦除

```c
void Block_Multi_Erase(u32 addr,u32 len);
```

| 变量名 | 说明 |
| :--- | :--- |
| addr | 指定地址 |
| len | 擦除的数据长度 |

所属文件：dev\_flash.c

---

擦除指定扇区

```c
void Sector_Erase(unsigned long Dst)
```

所属文件：dev\_flash.c

---

打印字符串log

```c
void print_logo_str(u8 logo_s,u8 *str);
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| str | 字符串 |

所属文件：dev\_uartlogo.c

---

读取模块中下载好的固件包，并写入外部flash，return 0:无数据 1:成功  2:数据错误

```c
u8 READ_GSM_RAM(u8 *outdata,u16 *data_len);
```

| 变量名 | 说明 |
| :--- | :--- |
| outdata | 数据缓冲区 |
| data\_len | 读取数据长度 |

所属文件：driver\_gprs.c

---

打印log

```c
void print_logo(u8 logo_s,u8 *remind,u8 *data,u16 len,u8 logo_type);
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log类型 |
| remind | log的标题名称 |
| data | log数据 |
| len | log的长度 |
| logo\_type | log的数据形式（16进制、字符串、数字、时间） |

所属文件：dev\_uatlogo.c

---

恢复出厂模式，参数all为1时是恢复

```c
void restore_factory(u8 all);
```

所属文件：dev\_uartlogo.c

---

# 内部函数

读取flash一页数据（512字节）

```c
void ReadFlashOnePage(u32 addr,u32 *outdata)
```

| 变量名 | 说明 |
| :--- | :--- |
| addr | 读取数据地址 |
| outdata | 数据缓冲区 |

---

写入flash一页数据（512字节）

```c
void WriteFlashOnePage(u32 addr,u32 *indata)
```

| 变量名 | 说明 |
| :--- | :--- |
| addr | 写入数据地址 |
| indata | 写入数据 |

---

获取校验和

```c
u16 get_pack_sumer(u16 len,u8* data)
```

| 变量名 | 说明 |
| :--- | :--- |
| len | 数据长度 |
| data | 数据 |

---

计算flash数据校验和

```c
u8 check_update_sumer(void)
```

---

在线升级

从M26模块中拷贝更新程序数据到flash中，再进入BOOT升级程序。

返回: 0-程序校验错误  1-拷贝数据出错

```c
u8 save_update_data(void)
```

---











