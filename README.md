# 沙发鱼霸API文档

# 阅前必看

## 目录

- [首页](https://github.com/waitforu/docs/blob/master/index/index.md)
- [发送短信](https://github.com/waitforu/docs/blob/master/send_sms.md)
- [注册设备ID](https://github.com/waitforu/docs/blob/master/register.md)
- [版本内容](https://github.com/waitforu/docs/tree/master/version)
	- [获取版本号](https://github.com/waitforu/docs/tree/master/version/version.md)
	- [刷新token](https://github.com/waitforu/docs/tree/master/version/refresh.md)
- [榜单](https://github.com/waitforu/docs/tree/master/rank)
	- [获取总榜单](https://github.com/waitforu/docs/tree/master/rank/index.md)
	- [获取平均时长](https://github.com/waitforu/docs/tree/master/rank/ave.md)


## 公共信息

| 名称 | 描述 | 备注 |
| ---- | ---- | ---- |
| in | 字段所在位置 |  |
| header | 在头部 |  |
| params | 在衔接在链接上 |

### 公共头

#### api-version
```
type: string
require: true
default: v1
in: header
```

#### Authorization
```
type: string
require: false
default: Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
in: header
```

### 部分返回信息code表

| CODE  |    说明      | 备注  |
| ----- |    ----      | ---  |
| 200   | 请求成功     | data部分为返回数据，如果无data说明该请求不需要返回数据 |
| 400   | 请求失败    | message为简略错误信息，data中为详细错误信息 |
| 401   | 请求验证失败  | 同400 |
| 403   | 请求被拒绝  | 同400 |
| 404   | 请求链接不存在 | 同400 |
| 422   | 请求数据有误 | 同400 |
| 500   | 服务器错误 | 同400 |
