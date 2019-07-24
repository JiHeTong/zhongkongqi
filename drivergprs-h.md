# 宏定义常量

## 网络状态

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| GPRS\_TCP\_RECONNECT\_TICK\_XS | u8 | 网络重连超时时间 |
| GPRS\_TCP\_RECR\_TICK\_XS | u8 | 网络接收超时时间 |
| GPRS\_TICK\_TCP\_SEND\_WAIT\_ACK\_TIMEOUT | u8 | 发送网络数据超时时间 |
| GPRS\_STATE\_CMNET\_DISCONNECT | u8\(hex\) | 注册网络失败 |
| GPRS\_STATE\_CMNET\_CONNECT | u8\(hex\) | 注册网络成功 |
| GPRS\_STATE\_TCP\_DISCONNECT | u8\(hex\) | 断开平台连接 |
| GPRS\_STATE\_TCP\_CONNECT | u8\(hex\) | 连接平台 |
| GPRS\_STATE\_TCP\_RECEIVED | u8\(hex\) | 接收到平台数据 |
| GPRS\_STATE\_TCP\_SEND\_STATE\_NULL | u8\(hex\) | 发送网络数据前 |
| GPRS\_STATE\_TCP\_SEND\_STATE1 | u8\(hex\) | 发送网络数据后 |
| GPRS\_STATE\_TCP\_SEND\_STATE2 | u8\(hex\) | 发送网络数据成功 |
| GPRS\_DATA\_FLOW\_PATH\_RECE\_KEY | u8\(hex\) | 接收到服务端key |
| GPRS\_DATA\_FLOW\_PATH\_ENTER | u8\(hex\) | 登录成功 |
| GPRS\_DATA\_FLOW\_PATH\_TIMING | u8\(hex\) | 上报环境数据 |
| GPRS\_DATA\_ALLOW\_SEND\_TIMING | u8\(hex\) | 接收到key并成功登录 |
| GPRS\_DATA\_ALLOW\_SEND\_DATA | u8\(hex\) | 上报环境数据成功 |
| GPRS\_DATA\_LINE\_STATE | u8\(hex\) | 检测板发生变化 |
| GPRS\_DATA\_LINE\_ERROR | u8\(hex\) | 检测板发生错误 |

---

## 消息长度

**说明：以下变量类型都是u8类型**

| 变量名 | 说明 |
| :--- | :--- |
| MSG\_SIZE\_LEN | 消息大小的字符长度 |
| MSG\_MSGTYPE\_LEN | 消息类型字符长度 |
| MSG\_VERSION\_LEN | 版本号字符长度 |
| MSG\_PASSKEY\_LEN | 密钥长度 |
| MSG\_DATETIME\_LEN | 日期时间长度 |
| MSG\_SIM\_ICCID\_LEN | sim卡ccid长度 |
| MSG\_CONTROLLER\_ID\_LEN | 中控器ID长度 |
| MSG\_SOURCE\_LEN | 消息资源长度 |
| MSG\_COUNT\_LEN | 多个资源个数 |
| MSG\_RESULT\_LEN | 设置修改参数结果长度 |
| MSG\_SETINGTYPE\_LEN | 设置类型长度 |
| MSG\_UPTYPE\_LEN | 更新类型长度 |
| DEVICE\_ID\_LEN | 设备ID长度 |
| VALUE\_TYPE\_LEN | 指类型长度 |
| VALUE\_LEN | 值长度 |
| ALARM\_LEN | 报警长度 |

---

## 消息字段索引

**说明：以下数据变量类型都是u8**

| 变量名 | 说明 |
| :--- | :--- |
| MSG\_FORMAT\_INDEX\_LENGTH | 消息的起始位 |
| MSG\_FORMAT\_INDEX\_MSGTYPE | 消息类型索引 |
| MSG\_FORMAT\_INDEX\_MESSAGE | 消息索引 |
| MSG\_FORMAT\_INDEX\_CONTROLLER | 中控器id索引 |
| MSG\_FORMAT\_INDEX\_VERSION | 版本号索引 |
| MSG\_FORMAT\_INDEX\_PASSKEY | 密钥索引 |
| MSG\_FORMAT\_INDEX\_DATETIME | 日期时间索引 |
| MSG\_FORMAT\_INDEX\_ICCID | ICCID索引 |
| MSG\_FORMAT\_INDEX\_SOURCE | 资源索引 |
| MSG\_FORMAT\_INDEX\_COUNT | 资源个数索引 |
| MSG\_FORMAT\_INDEX\_DATA | 数据索引 |
| MSG\_FORMAT\_INDEX\_RESULT | 设置反馈结果索引 |
| MSG\_FORMAT\_INDEX\_DEVICE\_ID | 设备ID索引 |
| MSG\_FORMAT\_INDEX\_GET\_URL | 获取到的升级地址索引 |

---

## 命令

**说明：以下变量类型都为u8\(hex\)形式**

| 变量名 | 说明 |
| :--- | :--- |
| MSG\_SERVER\_KEY\_SIGNIN\_ENCRYPT | SERVER-&gt;CLIENT获取Key |
| MSG\_CLIENT\_SIGN\_IN | CLIENT-&gt;SERVER登陆认证 |
| MSG\_SERVER\_SIGN\_IN\_ACK | SERVER-&gt;CLIENT登陆认证应答 |
| MSG\_CLIENT\_ENVI\_STATUS | CLIENT-&gt;SERVER上报数据 |
| MSG\_SERVER\_ENVI\_STATUS\_ACK | SERVER-&gt;CLIENT上报数据应答 |
| MSG\_CLIENT\_PARA\_UPDATE | CLIENT-&gt;SERVER设置修改反馈 |
| MSG\_SERVER\_PARA\_UPDATE\_ACK | SERVER-&gt;CLIENT设置修改反馈应答 |
| MSG\_CLIENT\_REQUEST\_UNLOCK | CLIENT-&gt;SERVER开锁请求 |
| MSG\_SERVER\_REQUEST\_UNLOCK\_ACK | SERVER-&gt;CLIENT开锁请求应答 |
| MSG\_CLIENT\_GET\_UPDATE\_URL | CLIENT-&gt;SERVER获取升级地址 |
| MSG\_SERVER\_GET\_UPDATE\_URL\_ACK | CLIENT-&gt;SERVER返回升级地址应答 |
| MSG\_CLIENT\_HEART\_BEAT | SERVER-&gt;CLIENT返回升级地址 |
| MSG\_SERVER\_HEART\_BEAT\_ACK | SERVER-&gt;CLIENT心跳包应答 |

---

## 服务端向设备设置属性

**说明：以下变量类型都是u8\(hex\)类型**

| 变量名 | 说明 |
| :--- | :--- |
| SERVER\_CMD\_SET\_IP | 设置IP |
| SERVER\_CMD\_SET\_IPPORT | 设置端口 |
| SERVER\_CMD\_SET\_DATETIME | 设置日期时间 |
| SERVER\_CMD\_SET\_AUTOCHECK\_TIME | 设置自检时间 |
| SERVER\_CMD\_SET\_CERT\_TIME | 设置定时上报时间 |
| SERVER\_CMD\_SET\_SLEEP\_TIME | 设置休眠时间 |
| SERVER\_CMD\_SET\_FAULT\_TIME | 设置门锁异常检测时间 |
| SERVER\_CMD\_SET\_TEMPALARM\_VALUE | 设置温度阈值°C |
| SERVER\_CMD\_SET\_ANGLEALARM\_VALUE | 设置倾斜阈值（度） |
| SERVER\_CMD\_SET\_CHECK\_MASK | 设置检测掩码 |
| SERVER\_CMD\_SET\_RESET | 设置设备重启 |
| SERVER\_CMD\_SET\_LINE\_TIME | 设置线路检测时间 |
| SERVER\_CMD\_SET\_LINE\_VER | 下发检测板版本 |
| SERVER\_CMD\_SET\_USER\_OPER\_ID | 用户开锁ID |
| SERVER\_CMD\_SET\_batt\_VALUE | 设置电压报警阈值 |

---

## 报警资源

**说明：以下变量类型都为u8\(hex\)类型**

| 变量名 | 说明 |
| :--- | :--- |
| ALARM\_TIME | 定时检测 |
| ALARM\_VALUE | 阈值报警 |
| ALARM\_WATER | 水浸报警 |
| ALARM\_SHAKE | 震动报警 |
| ALARM\_SERVER\_UNLOCK | 远程开锁 |
| ALARM\_BLE\_UNLOCK | 蓝牙开锁 |
| ALARM\_MACHINE\_UNLOCK | 机械开锁 |
| ALARM\_LOCK | 关锁 |
| ALARM\_FAULT | 门、锁异常 |
| ALARM\_LINE\_STATE | 检测板状态 |
| ALARM\_LINE\_ERROR | 检测板错误 |
| ALARM\_LINE\_ON\_OFF | 检测板上/下线 |
| ALARM\_LINE\_ON\_STATE | 检测板上线+端子状态 |

---

## value类型

**说明：以下变量类型都为u8\(hex\)**

| 变量名 | 说明 |
| :--- | :--- |
| LOCK\_STATE | 锁状态 Value=0（关）、Value=1（开） |
| DOOR\_STATE | 门磁状态Value=0（关）、Value=1（开） |
| TEMP\_VALUE | 温度Value=温度值（°C） |
| ANGLE\_VALUE | 倾斜角度Value=角度值（度） |
| BATT\_VALUE | 电量Value=电量值（百分比0-100） |
| RSSI\_VALUE | 信号Value=信号值（百分比0-100） |
| SHAKE\_STATE | 震动状态Value=0（未震动）、Value=1（震动） |
| WATER\_STATE | 水浸状态Value=0（未水浸）、Value=1（水浸） |
| LINE\_VALUE | 检测板Value=检测值 |
| USER\_OPER\_ID | 用户开锁ID |
| SEND\_LINE\_VER | 设备上报检测板版本号 |

---

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| PASSKEY\_FACTOR | u8\(hex\) | 密钥计算 |
| DEVICE\_A\_ID | string | 设备A的ID |
| DEVICE\_B\_ID | string | 设备B的ID |
| NET\_STATUS\_DISCONNECT | u8 | 无连接网络 |
| NET\_STATUS\_NO\_SIM | u8 | 无sim卡 |
| NET\_STATUS\_CONNECT | u8 | 已经连接网络 |
| NET\_STATUS\_REGISTER | u8 | 已经注册，上传了心跳包 |
| NET\_STATUS\_GSM\_ERROR | u8 | gsm模块错误 |
| NET\_STATUS\_TCP\_CONNECT | u8 | 连接到平台 |
| NET\_STATUS\_TCP\_DISCONNECT | u8 | 无连接到平台 |

---

# 结构体

HTTP\_PARA（http参数）

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| HTTP\_URL\[\] | uint8\_t | http地址 |
| firmware\_name\[\] | uint8\_t | 固件名 |
| URL\_LEN | uint8\_t | http地址长度 |
| firmware\_len | uint8\_t | 固件文件名长度 |
| firmware\_size | uint32\_t | 固件大小 |
| filehandle | uint32\_t | M26模块RAM中的文件句柄  由AT+QFOPEN 指令返回的数据得到 |
| firmware\_sumer | uint16\_t | 校验和 |

---

TERM\_LINE\_DATA\_OPERATE（检测板信息）

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| line\_num\_change | u8 | 改变的线路数 |
| line\_num\_error | u8 | 错误的线路数 |
| line\_addr\_change\[\] | u8 | 改变的线路地址 |
| line\_addr\_error\[\] | u8 | 错误的线路地址 |
| line\_status\_compare\[\]\[\] | u8 | 映射检测板线路状态数据，用于比较状态有异常时上报 |

---

DATA\_SAVE\_LIST（保存数据）

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| save\_num | u8 | 保存数据条数 |
| save\_len\[\] | u16 | 保存长度 |
| save\_addr\[\] | u16 | 保存地址 |

---

# 声明全局变量

| 变量名 | 变量类型 | 说明 |
| :--- | :--- | :--- |
| Server\_version | uint32\_t | 服务端固件版本号 |
| Server\_passkey | uint32\_t | 服务端密钥 |
| Client\_version | uint32\_t | 客户端固件版本号 |
| Client\_passkey | uint32\_t | 客户端密钥 |
| Client\_datetime\[\] | uint8\_t | 客户端时间日期 |
| User\_oper\_id\[\] | uint8\_t | 用户开锁id |
| Server\_line\_ver\[\] | uint8\_t | 服务端检测板版本号 |
| Client\_line\_ver\[\] | uint8\_t | 客户端检测板版本号 |
| Client\_temp | s16 | 设备温度 |
| Client\_incline\_angle | s16 | 设备倾斜角度 |
| Client\_battery | uint16\_t | 设备电池百分比 |
| Para\_set\_result | uint32\_t | 0设置已修改，其他表示错误 |
| Para\_set\_mask | uint32\_t | 掩码值 |
| flag\_gprs\_state | uint8\_t | 网络状态标志 |
| flag\_gprs\_usart\_sending | uint8\_t | 网络数据发送中标志 |
| flag\_gprs\_initialed | uint8\_t | 网络初始化成功标志 |
| gprs\_command\_index | uint8\_t | gprs指令索引 |
| gprs\_tcp\_send\_tick\_fail | uint8\_t | 发送数据计时 |
| gprs\_tcp\_send\_tick\_heart | uint16\_t | 心跳计时 |
| gprs\_tcp\_sending\_len | uint16\_t | 发送数据长度 |
| Lock\_unlock\_type | uint8\_t | 解锁类型：0 - LOCK\_A    1 - LOCK\_B |
| gprs\_tcp\_rece\_wait\_flag | uint8\_t | 0 - 接收到数据  1-Tcp等待接收到服务器数据 |
| gprs\_tcp\_rece\_timeout | uint16\_t | Tcp接收数据超时时间 |
| gprs\_tcp\_timing\_upload\_tick | uint16\_t | 定时上报数据计时 |
| Client\_senddata\_flowpath | uint8\_t | 客户端上报数据，服务端应答标志 |
| Client\_value\_alarm\_send\_flag | uint8\_t | 阈值报警 |
| Client\_shake\_alarm\_send\_flag | uint8\_t | 震动报警 |
| Client\_water\_alarm\_send\_flag | uint8\_t | 水浸报警 |
| term\_line\_operate | TERM\_LINE\_DATA\_OPERATE（结构体） | 检测板信息 |
| line\_on\_flag | uint8\_t | 检测板在线标志 |
| line\_off\_flag | uint8\_t | 检测板离线标志 |
| upline\_error\_num | uint8\_t | 检测板升级错误数量 |
| Client\_line\_data\_send\_flag | uint8\_t | 上报检测板数据 |
| gprs\_data\_save | DATA\_SAVE\_LIST（结构体） | 保存数据信息 |
| flag\_envi\_data\_save\_flash | uint8\_t | 数据保存FLASH标志，1-保存 |
| gprs\_tcp\_tx\_buffer\[\] | uint8\_t | 上报数据缓冲区 |
| gprs\_tcp\_rx\_buffer\[\] | uint8\_t | 接收数据缓冲区 |

---

# 函数声明

设置网络接收数据超时时间

```c
void driver_set_recedata_timeout(u16 time);
```

---

网络数据接收超时

```c
void driver_tcp_recedata_timeout(void);
```

---

网络更新超时

```c
void driver_tcp_update_timeout(void);
```

---

网络初始化

```c
void driver_gprs_initial(void);
```

---

登录认证

```c
void driver_gprs_sign_in_data_to_server(uint32_t command);
```

---

上报环境数据

```c
void driver_gprs_envi_status_data_to_server(uint32_t command,uint32_t source);
```

| 变量名 | 说明 |
| :--- | :--- |
| command | 协议指令 |
| source | 资源数据 |

---

上报单个环境数据

```c
void driver_gprs_one_alarm_data_to_server(uint32_t command,uint32_t source,uint8_t *id,uint32_t value_type,uint8_t *value);
```

| 变量名 | 说明 |
| :--- | :--- |
| command | 协议指令 |
| source | 资源数据 |
| id | 检测板id |
| value\_type | value类型 |
| value | value数据 |

---

服务端设置客户端结果反馈

```c
void driver_gprs_para_set_result_data_to_server(uint32_t command);
```

---

开锁请求

```c
void driver_gprs_request_unlock_data_to_server(uint32_t command,uint8_t lock_type);
```

| 变量名 | 说明 |
| :--- | :--- |
| command | 协议指令 |
| lock\_type | 锁类型（A锁或B锁） |

---

获取服务端固件更新包

```c
void driver_gprs_get_url_data_to_server(uint32_t command);
```

---

向服务端发送心跳包

```c
void driver_gprs_heartbeat_data_to_server(uint32_t command);
```

---

网络连接等一系列指令操作及接收网络数据解析

```c
void driver_gprs_usart_rx_analysis(void);
```

---

从服务端下载固件升级包

```c
void driver_gprs_http_download_machine(void);
```



