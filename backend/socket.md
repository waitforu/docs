# Socket
```
请求地址: ws://212.64.81.173:9503?admin_id={admin_id}&access_token={access_token}
```
### 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| admin_id | int | 是 | params | - | 管理员ID |
| access_token | string | 是 | params | - | access_token(**非拼接串**) |

### 接收参数

- [心跳输入值 'heartbeat'](https://github.com/waitforu/docs/blob/master/backend/socket.md#心跳输入)

### 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| id | int | 否 | 故障ID |
| reported_at | string | 否 | 上报时间 |
| fp_id | int | 否 | 钓台ID |
| name | string | 否 | 渔场名称 |
| des | string | 否 | 详细描述 |
| msg | string | 否 | 提示语 |
| onheartbeat | boolean | 否 | 心跳反应验证 |

### 范例

#### 链接地址
```
wsUrl = "ws://212.64.81.173:9503?admin_id=9999&access_token=82tGRl2kYi53L9e7US6VMPnNwga6oZyH";
```

#### 有人提交故障时
```
{
    "id": 6,
    "reported_at": "02.27 16:27:30",
    "fp_id": 5,
    "name": "设备2",
    "des": "操作故障",
    "msg": "用户上报5号钓台出现故障，请尽快处理"
}
```

#### 心跳输入
```
$ws_client->send('heartbeat');
```

#### 心跳反应
```
{
	"onheartbeat": true, // 只需要更改onheartbeat的值
}
```