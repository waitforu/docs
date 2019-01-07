# 沙发鱼霸API文档

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
拼接规则:base64(apikey:fisher_id:access_token)
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
	- [用户登录](https://github.com/waitforu/docs/tree/master/user/login.md)      **登录后多一条是否已绑定手机号字段**
	- [个人主页](https://github.com/waitforu/docs/tree/master/user/read.md)
	- [个人中心](https://github.com/waitforu/docs/tree/master/user/index.md)
	- [个人信息](https://github.com/waitforu/docs/tree/master/user/edit.md)
	- [修改个人信息](https://github.com/waitforu/docs/tree/master/user/update.md)
	- [用户登出](https://github.com/waitforu/docs/tree/master/user/logout.md)
- [我的渔币](https://github.com/waitforu/docs/tree/master/integration)
	- [渔币兑换](https://github.com/waitforu/docs/tree/master/integration/save.md)
	- [我的渔币](https://github.com/waitforu/docs/tree/master/integration/read.md)
	- [渔币兑换记录](https://github.com/waitforu/docs/tree/master/integration/index.md)
- [关注](https://github.com/waitforu/docs/tree/master/focus)
	- [关注钓手](https://github.com/waitforu/docs/tree/master/focus/save.md)
	- [查看是否已关注该钓手](https://github.com/waitforu/docs/tree/master/focus/read.md) **围观页面需要调取一次，查看是否已经关注垂钓中钓手**
	- [取关钓手](https://github.com/waitforu/docs/tree/master/focus/delete.md)
	- [关注列表](https://github.com/waitforu/docs/tree/master/focus/index.md)
- [时长](https://github.com/waitforu/docs/tree/master/time)
	- [我的时长](https://github.com/waitforu/docs/tree/master/time/index.md) **new**
- [订单](https://github.com/waitforu/docs/tree/master/orders)
	- [创建订单](https://github.com/waitforu/docs/tree/master/orders/save.md)
	- [充值记录](https://github.com/waitforu/docs/tree/master/orders/index.md)
- [钓鱼](https://github.com/waitforu/docs/tree/master/fishing)
	- [进入钓鱼](https://github.com/waitforu/docs/tree/master/fishing/save.md) **包括快速开始钓鱼，选择渔场钓鱼，选择钓台钓鱼** **new**
- [任务相关](https://github.com/waitforu/docs/tree/master/mission)
	- [获取任务列表](https://github.com/waitforu/docs/tree/master/mission/index.md) **new**
	- [领取任务奖励](https://github.com/waitforu/docs/tree/master/mission/update.md) **new**
- [绑定](https://github.com/waitforu/docs/tree/master/binding)
	- [绑定手机号](https://github.com/waitforu/docs/tree/master/binding/phone.md) **new**
- [围观](https://github.com/waitforu/docs/tree/master/onlook)
	- [进入围观](https://github.com/waitforu/docs/tree/master/onlook/save.md) **包括前去围观，选择渔场围观(即直接通过渔场开始围观)，搜索钓手号或者手机号围观（需要完整的手机号）** **new**
