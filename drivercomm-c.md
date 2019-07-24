# 说明

该文件功能比较多，包括网络、开锁、获取设备信息、告警、检测检测板

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| flag\_module\_start | uint8\_t | 模块启动标志 |
| dce\_sim\_ccid\[\] | uint8\_t | sim卡ccid |
| DCE\_COMMAND\[\] | uint8\_t\* | 网络AT指令集 |
| flag\_water\_state | uint8\_t | 水浸状态壮志 |
| flag\_water\_state\_last | uint8\_t | 水浸最后状态标志 |
| water\_alarm\_flag | uint8\_t | 水浸报警标志 |
| water\_alarm\_tick | uint16\_t | 水浸报警超时时间 |
| shake\_alarm\_flag | uint8\_t | 震动报警标志 |
| shake\_alarm\_tick | uint16\_t | 震动报警超时时间 |
| dce\_error\_cnt | uint16\_t | 网络命令错误重发计数 |
| gprs\_tcp\_connect\_timeout | uint16\_t | 网络连接超时时间 |
| shake\_state\_flag | uint8\_t | 震动状态标志 |
| shake\_alarm\_send\_done\_flag | uint8\_t | 震动报警发送完成标志 |
| signal\_read\_time | uint8\_t | 信号读取超时时间 |
| signal\_check\_flag | uint8\_t | 检查信号标志 |
| auto\_check\_line\_ver\_cnt | uint8\_t | 检测板自检 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| Enter\_sleep\_flag | uint8\_t | 休眠标志 | main.c |
| net\_invalid\_sleep\_flag | uint8\_t | 网络无效标志 | main.c |
| BT\_status\_led | uint8\_t | 蓝牙状态指示灯 | driver\_bluetooth.c |
| logo\_flag | uint8\_t | log标志 | dev\_uartlogo.c |
| system\_para | SYSTEM\_PARA（结构体） | 系统信息参数 | driver\_upgrade.c |
| term\_line\_data | TERM\_LINE\_LIST（结构体） | 检测板信息 | driver\_upgrade.c |

---

# 外部函数

延时毫秒

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

设置网络状态

```c
void set_net_status(u8 st);
```

所属文件：driver\_gprs.c

---

设置休眠等待超时

```c
void set_sleep_wait_timeout(uint16_t time);
```

所属文件：main.c

---

设置网络信号

```c
void set_signel_data(u8 *data);
```

所属文件：dev\_uartlogo.c

---

打印字符串log

```c
void print_logo_str(u8 logo_s,u8 *str);
```

| 变量名 | 说明 |
| :--- | :--- |
| logo\_s | log标志 |
| str | 字符串 |

所属文件：dev\_uartlogo.c

---

处理定时上报失败

```c
void RTC_AlarmHandle(void)
```

所属文件：SinRTC.c

---

# 内部函数

向gsm模块发送指令

```c
void driver_dce_usart_send_buffer(uint8_t cmd_index)
```

---

主循环中gsm模块启动操作

```c
void driver_dce_usart_rx_analysis(void)
```

---

检查网络发送数据

```c
void check_net_sta_send_data(void)
```

---

检测检测板

```c
void driver_line_status_check_machine(void)
```

---

自检、阈值报警

```c
void driver_value_state_machine(void)
```

---

















