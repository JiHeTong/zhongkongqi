# 函数声明

1小时中断一次

```c
void set_time_alarm(void)
```

---

闹钟初始化

```c
void SinRTC_Initial(void);
```

---

获取设备当前时间

```c
void SinRTC_GetTime(uint16_t *len, uint8_t *Timebuf);
```

| 变量名 | 说明 |
| :--- | :--- |
| len | 长度（没有实际用处） |
| Timebuf | 获取时间的数据缓冲区 |

---

给设备设置时间

```c
uint8_t SinRTC_SetTime(uint16_t *len, uint8_t *Timebuf);
```

| 变量名 | 说明 |
| :--- | :--- |
| len | 时间数据长度 |
| Timebuf | 设置的时间数据 |

---

