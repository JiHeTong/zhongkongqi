# 宏定义常量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| LOCK\_KEY\_REQUEST\_TIME | u8 | 按键请求超时 |
| OPEN\_LOCK\_TIME | u8 | 开锁超时 |
| LOCK\_LED\_OFF | u8 | 关闭开锁指示灯 |
| LOCK\_LED\_BLINK | u8 | 开锁指示灯闪烁 |
| LOCK\_LED\_ON | u8 | 点亮开锁指示灯 |
| LOCK\_UNKNOW | u8\(hex\) | 状态未知 |
| LOCK\_OPEN | u8\(hex\) | 锁开/浸水 |
| LOCK\_CLOSE | u8\(hex\) | 锁关/不浸水 |
| TYPE\_A | u8 | 锁/门 A |
| TYPE\_B | u8 | 锁/门 B |

---

# 声明全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| LockA\_led\_state | uint8\_t | A锁指示灯状态 |
| LockB\_led\_state | uint8\_t | B锁指示灯状态 |
| LockA\_request\_flag | uint8\_t | A锁请网络开锁求标志 |
| LockB\_request\_flag | uint8\_t | B锁请求网络开锁标志 |
| iic\_irq\_sta\_flag | uint8\_t | 检测板状态变化产生中断 |
| iic\_irq\_err\_flag | uint8\_t | 检测板拔插产生中断 |

---

# 函数声明

设置A锁指示灯状态

```c
void set_lockA_led_status(uint8_t status,uint16_t time);
```

| 变量名 | 说明 |
| :--- | :--- |
| status | 状态 |
| time | 关闭指示灯时间 |

---

设置B锁指示灯状态，参数同上

```c
void set_lockB_led_status(uint8_t status,uint16_t time);
```

---

读取锁状态，lock\_type为锁类型（A锁或B锁）

```c
uint8_t read_lock_status(uint8_t lock_type);
```

---

读取门状态，door\_type为门类型（A门或B门）

```c
uint8_t read_door_status(uint8_t door_type);
```

---

读取水浸状态

```c
uint8_t read_water_status(void);
```

---

门锁、水浸初始化

```c
void driver_lock_door_water_init(void);
```

---

按键开锁初始化

```c
void driver_lock_key_init(void);
```

---

iic检测板初始化

```c
void driver_iic_line_com_irq_init(void);
```

---

按键开锁超时

```c
void driver_lock_key_timeout(void);
```

---

A锁开锁控制，hight\_time为自动关锁时间

```c
uint8_t open_lock_A(uint16_t high_time);
```

---

B锁开锁控制，hight\_time为自动关锁时间

```c
uint8_t open_lock_B(uint16_t high_time);
```



