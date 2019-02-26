# 沙发鱼霸后台管理APP——API文档

# 阅前必看

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
拼接规则:base64(apikey:admin_id:access_token)
in: header
```

### 部分返回信息code表

| CODE  |    说明      | 备注  |
| ----- |    ----      | ---  |
| 200   | 请求成功     | data部分为返回数据，如果无data说明该请求不需要返回数据 |
| 400   | 请求失败    | message为简略错误信息，data中为详细错误信息 |
| 401   | 请求验证失败  | 同400 |
| 302   | 渔场/钓台已满  | 同400 |
| 403   | 请求被拒绝  | 同400 |
| 404   | 请求链接不存在 | 同400 |
| 408   | 请求超时 | 同400 |
| 422   | 请求数据有误 | 同400 |
| 430   | 任务列表，链接需要跳转 | 同400 |
| 500   | 服务器错误 | 同400 |

## 目录

- [首页](https://github.com/waitforu/docs/blob/master/backend/index/index.md)
- [登陆](https://github.com/waitforu/docs/blob/master/backend/login/save.md)
- [上报故障](https://github.com/waitforu/docs/tree/master/backend/report/save.md)
- [故障](https://github.com/waitforu/docs/tree/master/backend/fault)
	- [故障问题](https://github.com/waitforu/docs/tree/master/backend/fault/create.md)
	- [故障处理](https://github.com/waitforu/docs/tree/master/backend/fault/update.md)
	- [操作解决](https://github.com/waitforu/docs/tree/master/backend/fault/read.md)