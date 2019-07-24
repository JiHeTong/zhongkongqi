# 宏定义常量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| TIME\_1MS\_FLAG | u8\(hex\) | 1毫秒标志 |
| TIME\_10MS\_FLAG | u8\(hex\) | 10毫秒标志 |
| TIME\_100MS\_FLAG | u8\(hex\) | 100毫秒标志 |
| TIME\_1S\_FLAG | u8\(hex\) | 1秒标志 |
| SYSTICK\_USART\_RECEIVE\_END\_EXPIRED | u8 | 串口接收数据完成标志 |

---

# 结构体

计时器数据

TIMER\_DATA

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| time\_1ms\_cnt |  unsigned char | 每毫秒计数 |
| time\_10ms\_cnt |  unsigned char | 每10毫秒计数 |
| time\_100ms\_cnt |  unsigned char | 每100毫秒计数 |
| time\_1s\_cnt |  unsigned char | 每秒计数 |
| time\_flag |  unsigned char | 时间标志 |

---

# 函数声明

延时毫秒

```c
void driver_systick_delay_xms(uint32_t xms);
```

---



