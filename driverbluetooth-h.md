# 宏定义常量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| UARTBUFSIZE | u16 | 蓝牙串口缓冲区大小 |

---

# 函数定义

向蓝牙设备发送数据

```c
void SinBTApi_Print(uint16_t DataLen, uint8_t *Data);
```

| 变量名 | 说明 |
| :--- | :--- |
| DataLen | 数据长度 |
| Data | 数据 |

---

蓝牙模块初始化

```c
void SinBTApi_Initial(void);
```

---

关闭蓝牙模块

```c
void SinBTApi_Close(void);
```

---

读取蓝牙状态

```c
int read_blue_status(void);
```

---

解析蓝牙接收到的数据

```c
void proc_blue_rece_data(u8 *data,u16 datalen);
```

| 变量名 | 说明 |
| :--- | :--- |
| data | 接收到的数据 |
| datalen | 数据长度 |

---

蓝牙接收超时

```c
void dec_blue_timeout(void);
```

---

封装的检查蓝牙状态和解析蓝牙数据

```c
int check_uart_timeout(void);
```

---

在主循环中，封装的蓝牙全部操作

```c
void driver_bt_state_machine(void);
```

---



