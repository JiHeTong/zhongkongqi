# 函数声明

打开检测板io口

```c
void check_io_init(void);
```

---

关闭检测板io口

```c
void check_io_close(void);
```

---

获取检测板版本号，返回1为成功，0为失败

```c
u8 read_device_ver(u8 device_addr,u8 *id,u8 *ver)
```

| 变量名 | 说明 |
| :--- | :--- |
| device\_addr | 检测板地址 |
| id | 检测板id |
| ver | 检测板版本号缓冲区 |

---

读取检测板id，返回1为成功，0为失败

```c
u8 read_device_id(u8 device_addr,u8 *id,u8 *ret_id)
```

| 变量名 | 说明 |
| :--- | :--- |
| device\_addr | 检测板地址 |
| id | 默认id |
| ret\_id | 读取id的缓冲区 |

---

给检测板设置id， 返回1为成功，0为失败

```c
u8 set_device_id(u8 device_addr,u8 *id,u8 *set_id);
```

| 变量名 | 说明 |
| :--- | :--- |
| device\_addr | 检测板地址 |
| id | 默认id |
| set\_id | 设置id |

---

添加检测线路，返回0为成功，非0为失败

```c
u8 add_line_data(u8 *id,u8 side);
```

| 变量名 | 说明 |
| :--- | :--- |
| id | 检测板id |
| side | 检测板方向 |

---

删除检测线路

```c
u8 del_line_data(u8 *id)
```

---

出厂检测板更改ID，返回0为成功，非0失败

```c
u8 line_id_amend(u8 *id)
```

---

获取指定ID线路方向，返回0成功，1失败

```c
u8 get_one_line_side(u8 *id,u8 *side)
```

| 变量名 | 说明 |
| :--- | :--- |
| id | 检测板id |
| side | 方向缓冲区 |

---

设置指定ID线路方向，返回0成功，非0失败

```c
u8 set_one_line_side(u8 *id,u8 side)
```

| 变量名 | 说明 |
| :--- | :--- |
| id | 检测板id |
| side | 方向 |

---

获取指定ID线路状态，返回0为成功，1为失败

```c
u8 get_one_line_status(u8 *id,u8 *status)
```

| 变量名 | 说明 |
| :--- | :--- |
| id | 检测板id |
| status | 检测板状态缓冲区 |

---

获取指定ID线路状态和方向，返回0为成功，1为失败

```c
u8 get_one_line_status2(u8 *id,u8 *status,u8 *side)
```

| 变量名 | 说明 |
| :--- | :--- |
| id | 检测板id |
| status | 检测板状态缓冲区 |
| side | 检测板方向缓冲区 |

---

获取所有线路状态

```c
void get_all_line_status(void)
```

---

获取检测板版本号

```c
void get_line_ver(void);
```

---

获取所有检测板版本号

```c
void get_all_line_ver(void);
```

---

重置检测板数据

```c
void line_reset_data_list(void)
```

---

获取检测板数据列表

```c
void setup_line_init(void)
```

---

恢复指定id检测板出厂设置，返回0为成功，1为失败

```c
u8 one_line_factory(u8 *id)
```

---

升级所有检测板

```c
u8 *update_all_check(u32 flash_addr)
```

---

串口升级检测板，返回0为成功，1为失败

```c
uint8_t save_uart_updata_linedata(u8 start_f,u8 *data,u16 len);
```

| 变量名 | 说明 |
| :--- | :--- |
| start\_f | 起始位（没有实际意义） |
| data | 更新数据 |
| len | 数据长度（没有实际意义） |

---

在下线升级检测板，up\_result位更新结果，返回0为成功，非0为失败

```c
uint8_t save_line_update_data(u8 *up_result)
```

---





















