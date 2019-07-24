# 说明

该文件主要用作闹钟，获取设备当前时间，给设备设置时间等操作

---

# 内全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| Bit\_Flag1 | u8 | 闰年闰月标志位 |
| FLAG\_LEAPYEAR | u8\(hex\) | 闰年标志 |
| month\_inc | u8\(hex\) | 闰月标志 |
| days\_mon\[12\] | unsigned char | 各个月份的天数 |
| RTC\_Alarm\_flag | uint8\_t | 定时报警标志 |
| RTC\_Alarm\_time\_tick | uint16\_t | 报警计时累加 |

---

# 外部全局变量

| 变量名 | 变量类型 | 说明 | 所属文件 |
| :--- | :--- | :--- | :--- |
| reset\_timeout | uint16\_t | 重启设备时间累加 | driver\_gprs.c |
| check\_timing\_upload\_err\_timeout | uint16\_t | 重新登录时间累加 | driver\_gprs.c |
| flag\_module\_start | uint8\_t | gsm模块重启标志 | driver\_comm.c |

---

# 外部函数

延时毫秒

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

# 内部函数

定时报警处理

```c
void RTC_AlarmHandle(void)
```

---

定时中断函数

```c
void RTC_IRQHandler(void)
```

---

判断年份是否为闰年，返回1为闰年，返回0为非闰年

```c
 u8 leapyear(s16 nYear)
```

---

计算周数，传入年、月、日

```c
int ymdtowday(int nYear, int nMonth, int nMday)
```

---



