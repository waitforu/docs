# Socket
## 钓鱼者
```
请求地址: ws://212.64.81.173:9501?fishing_id={fishing_id}&ws_fp_id={fp_id}&access_token={access_token}
```
### 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| fishing_id | int | 是 | params | - | 钓手号 |
| ws_fp_id | int | 是 | params | - | 钓台编号 |
| access_token | string | 是 | params | - | access_token(**非拼接串**) |

### 接收参数

- [钓手心跳输入值 'heartbeat'](https://github.com/waitforu/docs/blob/master/socket.md#钓手心跳输入)
- [限位推送](https://github.com/waitforu/docs/blob/master/socket.md#限位推送)
- [发送消息 'op_type'](https://github.com/waitforu/docs/blob/master/socket.md#发送消息-垂钓者)
- [**广播**](https://github.com/waitforu/docs/blob/master/socket.md#广播) **new**
- [**动作完成指令推送**](https://github.com/waitforu/docs/blob/master/socket.md#动作完成指令推送) **new**

### 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| ws_fisher_id | int | 否 | 钓手号 |
| ws_onlook | int | 否 | 围观人数 |
| ws_likes | int | 否 | 点赞人数 |
| ws_fish_num | int | 否 | 钓鱼数 |
| onheartbeat | boolean | 否 | 心跳反应验证 |
| timestr | string | 否 | 剩余时长提示 |
| ws_limit | int | 否 | 只有新手指引时才有，1 提竿限位响应，2 上饵限位响应，3 抛竿限位响应 |
| messages | array | 否 | 消息内容 |
|　├─name | string | 是 | 昵称 |
|　├─msg | string | 是 | 消息主体 |
|　└─msg_type | string | 是 | 消息类型: message - 文本 |

### 范例

#### 链接地址
> 测试

```
wsUrl = "ws://148.70.13.176:9501?fishing_id=67224273&ws_fp_id=1&access_token=L5pnaJx5M2hb6wdguU6NHjRskEK4XcG7";
```

> 正式

```
wsUrl = "ws://212.64.81.173:9501?fishing_id=67224273&ws_fp_id=1&access_token=L5pnaJx5M2hb6wdguU6NHjRskEK4XcG7";
```

#### 首次进入返回值
```
{
	"ws_fisher_id":"67224273",
	"ws_onlook":0,
	"ws_likes":0,
	"ws_fish_num":0,
	'timestr': "您的剩余时长不足10分钟", // 如果时长不够时会产生该字段
}
```
#### 钓手心跳输入
```
$ws_client->send('heartbeat');
```

#### 心跳反应
```
{
	"onheartbeat": true, // 只需要更改onheartbeat的值
}
```

#### 发送消息-垂钓者
```
客户端发送:
var data = {
	"op_type": "talk"
	, "msg": "You are right"
	, "msg_type": "message"
};
$ws_client->send(JSON.stringify(data));

服务端推送内容:
{
	"messages":{
		"name":"sf_BGROT"  // 发言者名称，
		, "avatar": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/icon.png" // 发言者头像
		, "msg": "you are right" // 消息内容
		, "msg_type": "message" // 消息类型
	}
}
该钓台所有人都会收到该信息
```

#### 广播
```
{
	"broadcast":
	{
		"content": "倒计时10分钟开始",
		"btn_name": "", // 按钮名称为空，则无按钮，按钮直接加文本末端
		"btn_link": "",
	}
}
或者
{
	"broadcast":
	{
		"content":"您的剩余时长不足10分钟",
		"btn_name":"点击充值", // 按钮名称为空，则无按钮，按钮直接加文本末端
		"btn_link":"1"
	}
}
```

#### ~~剩余时长不足时~~
```
{
	"timestr": "您的剩余时长不足10分钟", // 如果时长不够时会产生该字段
}
```

#### 动作完成指令推送
```
{
	"now_cmd"： "03", // 当前指令位置 03复位，04上饵，05抖饵，06垂钓，07刺鱼，08提鱼，09抄鱼，0a摘鱼，02收鱼成功
	"now_status": "02" // 指令状态 00 下发 01 指令进行中 02 已完成
}
```

#### 有围观人进入时
```
{
	"ws_onlook":1, // 只需要更改ws_onlook的值
}
```

#### 有围观人点赞时
```
{
	"ws_likes":1, // 只需要更改ws_likes的值
}
```
#### 有围观人退出时
```
{
	"ws_onlook": 1, // 只需要更改ws_onlook的值
}
```

#### 当钓手退出时
```
onclose响应事件，此时前端应关闭页面
```

#### 限位推送
```
{
	"ws_limit": 1, // 1 是提竿限位，2 上饵限位，4 抛竿限位
}
```

## 围观
```
请求地址: ws://212.64.81.173:9501?onlook_id={onlook_id}&ws_fp_id={fp_id}&access_token={access_token}
```
### 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| onlook_id | int | 是 | params | - | 围观者钓手号 |
| ws_fp_id | int | 是 | params | - | 钓台编号 |
| access_token | string | 是 | params | - | access_token(**非拼接串**) |

### 接收参数

- [心跳输入值 'heartbeat'](https://github.com/waitforu/docs/blob/master/socket.md#心跳输入)
- [切换围观 'op_type'](https://github.com/waitforu/docs/blob/master/socket.md#切换围观钓台输入)
- [点赞输入 'op_type'](https://github.com/waitforu/docs/blob/master/socket.md#自己点赞)
- [发送消息 'op_type'](https://github.com/waitforu/docs/blob/master/socket.md#发送消息-围观者)

### 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| ws_fisher_id | int | 否 | 钓手号 |
| ws_onlook | int | 否 | 围观人数 |
| ws_likes | int | 否 | 点赞人数 |
| ws_fish_num | int | 否 | 钓鱼数 |
| onheartbeat | boolean | 否 | 心跳反应验证 |
| messages | array | 否 | 消息内容 |
|　├─name | string | 是 | 昵称 |
|　├─msg | string | 是 | 消息主体 |
|　└─msg_type | string | 是 | 消息类型: message - 文本 |

### 范例

#### 链接地址

> 测试

```
wsUrl = "ws://148.70.13.176:9501?onlook_id=9678212&ws_fp_id=1&access_token=RDFqp8nTh94XkU7AmeEycs5zxQ33MZ6w";
```

> 正式

```
wsUrl = "ws://212.64.81.173:9501?onlook_id=9678212&ws_fp_id=1&access_token=RDFqp8nTh94XkU7AmeEycs5zxQ33MZ6w";
```

#### 首次进入返回值
```
{
	"ws_fisher_id":"67224273",
	"ws_onlook":1,
	"ws_likes":0,
	"ws_fish_num":0,
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

#### 发送消息-围观者
```
客户端发送:
var data = {
	"op_type": "talk"
	, "msg": "You are right"
	, "msg_type": "message"
};
$ws_client->send(JSON.stringify(data));

服务端推送内容:
{
	"messages":{
		"name":"sf_BGROT"  // 发言者名称，
		, "avatar": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/icon.png" // 发言者头像
		,"msg":"you are right" // 消息内容
		,"msg_type":"message" // 消息类型
	}
}
该钓台所有人都会收到该信息
```

#### 有围观人进入时
```
{
	"ws_onlook": 2, // 只需要更改ws_onlook的值
}
```

#### 切换围观钓台输入
```
$ws_client->send('{"op_type": "cutover", "ws_fp_id": 2}');
```

#### 切换围观返回
```
{
	"ws_fisher_id":"67224273",
	"ws_onlook":1,
	"ws_likes":0,
	"ws_fish_num":0,
}
```

#### 自己点赞
```
$ws_client->send('{"op_type": "like"}');
```

#### 自己点赞响应
```
{
	"ws_likes": 1, // 只需要更改ws_likes的值
}
```

#### 有围观人点赞时
```
{
	"ws_likes": 2, // 只需要更改ws_likes的值
}
```

#### 有围观人退出时
```
{
	"ws_onlook": 1, // 只需要更改ws_onlook的值
}
```

#### 当正在钓鱼的钓手退出时
```
onclose响应事件，此时前端应关闭页面
```

#### 当自己退出时
```
onclose响应事件，此时前端应关闭页面
```