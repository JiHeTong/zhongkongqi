# 说明

该文件主要用作门锁的操作

---

# 内部全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| KeyA\_request\_flag | uint8\_t | LOCK\_A按键按下 |
| KeyA\_request\_cnt | uint16\_t | A锁按键按下3s请求开锁 |
| LockA\_led\_cnt | uint16\_t | A锁自动关闭指示灯的时间 |
| KeyB\_request\_flag | uint8\_t | LOCK\_B按键按下 |
| KeyB\_request\_cnt | uint16\_t | B锁按键按下3s请求开锁 |
| LockB\_led\_cnt | uint16\_t | B锁自动关闭指示灯的时间 |
| lock\_status\[\] | uint8\_t | A锁和B锁的状态集合 |
| door\_status\[\] | uint8\_t | A门和B门的状态集合 |
| water\_status | uint8\_t | 水浸状态 |
| power\_input\_status | uint8\_t | 电量输入状态 |

---

# 外部函数声明

延时毫秒

```c
void delay_ms(u16 ms);
```

所属文件：main.c

---

延时微秒

```c
void delay_us(u16 us);
```

所属文件：main.c

---

看门狗重置

```c
void SinWatchDog_Reset(void);
```

所属文件：driver\_timer.c

---

















