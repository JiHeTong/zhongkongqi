# 说明

该文件主要用做中断处理，超时操作

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| timer2\_data | TIMER\_DATA（结构体） | 计时数据 |
| time\_1s\_cnt | int | 毫秒累加计数，1000次为1秒 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| Enter\_sleep\_flag | uint8\_t | 进入休眠标志 | main.c |
| RTC\_Alarm\_flag | uint8\_t | 定时报警标志 | SinRTC.c |

---

# 外部函数声明

延时毫秒

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

进入休眠等待超时

```c
void enter_sleep_wait_timeout(void);
```

所属文件：main.c

---

usb连接超时

```c
void usb_connect_timeout(void);
```

所属文件：main.c

---

串口接收数据超时

```c
void dec_uartdebug_timeout(void);
```

所属文件：dev\_uartlogo.c

---

# 内部函数声明

网络模块启动命令发送超时

```c
void driver_timer0_dce_sending_timeout(void)
```

---

网络模块连接命令发送超时

```c
void driver_timer0_gprs_sending_timeout(void)
```

---

自检超时

```c
void driver_timer0_adc_timeout(void)
```

---

中断一秒

```c
void SysTick_1s_IRQHandler(void)
```

---

串口接收数据超时

```c
void driver_systick_usart_rx_check_finished(void)
```

---

系统中断函数

```c
void SysTick_Handler(void)
```

---

看门狗初始化

```c
void iwdg_init(void)
```

---

看门狗重置

```c
void SinWatchDog_Reset(void)
```

---



