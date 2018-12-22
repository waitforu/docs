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
- [用户信息](https://github.com/waitforu/docs/tree/master/user)
	- [用户登录](https://github.com/waitforu/docs/tree/master/user/login.md)
	- [个人主页](https://github.com/waitforu/docs/tree/master/user/read.md)
	- [个人中心](https://github.com/waitforu/docs/tree/master/user/index.md)
	- [个人信息](https://github.com/waitforu/docs/tree/master/user/edit.md)
	- [修改个人信息](https://github.com/waitforu/docs/tree/master/user/update.md)
	- [用户登出](https://github.com/waitforu/docs/tree/master/user/logout.md)
- [我的积分](https://github.com/waitforu/docs/tree/master/integration)
	- [用户登录](https://github.com/waitforu/docs/tree/master/integration/save.md)
	- [我的积分](https://github.com/waitforu/docs/tree/master/integration/read.md)
	- [积分兑换记录](https://github.com/waitforu/docs/tree/master/integration/index.md)
- [关注](https://github.com/waitforu/docs/tree/master/focus)
	- [用户登录](https://github.com/waitforu/docs/tree/master/focus/save.md)
	- [我的积分](https://github.com/waitforu/docs/tree/master/focus/read.md)
	- [关注列表](https://github.com/waitforu/docs/tree/master/focus/index.md)

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
