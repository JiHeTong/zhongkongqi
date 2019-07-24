# 宏定义常量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| DCE\_STATE\_CLOSE | u8\(hex\) | 关回显 |
| DCE\_STATE\_OPEN | u8\(hex\) | 开回显 |
| DCE\_NO\_SIM | u8\(hex\) | 无sim卡 |
| DCE\_SIM\_OK | u8\(hex\) | 有sim卡 |
| DCE\_TICK\_SEND\_WAIT\_ACK\_TIMEOUT | u8 | 发送等待超时时间 |

---

# 枚举

DCE\_COMMAND\_INDEX

命令操作符

| 变量名 | 说明 |
| :--- | :--- |
| AT\_DCE\_ACK\_NOT\_REPEAT\_DTE\_COMMAND | 关回显 |
| AT\_DCE\_ACK\_REPEAT\_DTE\_COMMAND | 开回显 |
| AT\_DCE\_ACK\_SIM\_COMMAND | 检查是否安装sim卡命令 |
| AT\_DCE\_ACK\_SET\_BAUDRATE | 设置波特率 |
| AT\_DEC\_SLEEP\_MODE | 慢时钟配置 |
| AT\_DEC\_GET\_CCID | 显示CCID |
| AT\_DEC\_GET\_CSQ | 获取信号 |
| AT\_DCE\_GET\_REGISTER | GPRS 网络注册状态 |
| AT\_DCE\_SET\_QCFG | 查询运营商列表 |

---

LOCK\_STATE\_FLAG

解锁状态标志

| 变量名 | 说明 |
| :--- | :--- |
| LOCK\_STATE\_INVALID | 无效 |
| LOCK\_STATE\_OPEN | 打开 |
| LOCK\_STATE\_CLOSE | 关闭 |
| LOCK\_STATE\_ERROR | 错误 |

---

ALARM\_STATE\_FLAG

告警状态标志

| 变量名 | 说明 |
| :--- | :--- |
| ALARM\_STATE\_INVALID | 无效 |
| ALARM\_STATE\_ABNORMAL | 反常 |
| ALARM\_STATE\_NORMAL | 正常 |

---

# 声明全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| flag\_dce\_state | uint8\_t | 回显状态标志 |
| flag\_dce\_usart\_sending | uint8\_t | 发送中标志 |
| dce\_command\_index | uint8\_t | 命令索引 |
| dce\_usart\_send\_tick\_fail | uint8\_t | 发送数据超时累加 |
| Wifi\_signal | uint8\_t | 网络信号 |
| gsm\_restart\_cnt | uint8\_t | gsm重新启动计数 |
| gprs\_tcp\_connect\_state\_flag | uint8\_t | 网络连接状态标志 |
| module\_init\_read\_time | uint8\_t | 模块启动超时 |
| module\_init\_check\_flag | uint8\_t | 模块启动检查标志 |
| lock\_door\_state\_other\_tick\_valid | uint16\_t | 门锁异常检测时间 |
| auto\_need\_check\_tick\_valid | uint16\_t | 自检时间 |
| gprs\_tcp\_timing\_upload\_tick\_valid | uint16\_t | 定时上报时间 |
| line\_state\_need\_check\_tick\_valid | uint16\_t | 检测板检测时间 |
| sleep\_need\_check\_tick\_valid | uint16\_t | 等待进入睡眠时间 |
| flag\_lock\_A\_state | uint8\_t | A锁状态标志 |
| flag\_lock\_A\_state\_last | uint8\_t | A锁最后状态标志 |
| Lock\_A\_unlock\_flag | uint8\_t | A锁开锁标志 |
| flag\_lock\_B\_state | uint8\_t | B锁状态标志 |
| flag\_lock\_B\_state\_last | uint8\_t | B锁最后状态标志 |
| Lock\_B\_unlock\_flag | uint8\_t | B锁开锁标志 |
| Unlock\_A\_type\_flag | uint32\_t | A锁开锁类型 |
| Unlock\_B\_type\_flag | uint32\_t | B锁开锁类型 |
| tick\_auto\_need\_check | uint16\_t | 自检超时累加 |
| flag\_auto\_need\_check | uint8\_t | 自检标志 |
| tick\_line\_state\_need\_check | uint16\_t | 检测板自检超时累加 |
| flag\_line\_state\_need\_check | uint8\_t | 检测板自检标志 |
| flag\_lock\_operate\_line\_check | uint8\_t | 开/关门锁处罚检测板检测标志 |

---

# 函数声明

设置网络连接超时时间

```c
void driver_set_connect_timeout(u16 time);
```

---

网络连接超时

```c
void driver_tcp_connect_timeout(void);
```

---

开关回显，参数为1是开回显，0是关回显

```c
void driver_dce_initial(uint8_t flag_enable);
```

---

模块启动超时

```c
void dec_module_read_time(void);
```

---

设置模块启动超时时间

```c
void set_module_read_time(u8 time);
```

---

检查模块启动命令发送

```c
void check_module_read(void);
```

---

主循环中封装的网络模块启动命令操作

```c
void driver_dce_state_machine(void)
```

---

检查门锁状态

```c
void driver_lock_state_check(void);
```

---

主循环中锁状态的主要操作

```c
void driver_lock_state_machine(void);
```

---

主循环中水浸检测

```c
void driver_water_state_check(void)
```

---

检查水浸超时

```c
void water_check_timeout(void);
```

---

检测板检查超时

```c
void line_check_timeout(void);
```

---

主循环中检查设备状态和检测板状态信息

```c
void driver_term_state_check_update(void)
```

---

开机设备状态检测

```c
void driver_term_state_initial(void);
```

---

主循环中封装的报警和自检操作

```c
void driver_term_state_machine(void)
```

---

读取网络信号超时

```c
void dec_signal_read_time(void);
```

---

设置网络信号超时时间

```c
void set_signal_read_time(u8 time);
```

---

检查网络信号

```c
void check_signal_read_time(void);
```

---







