# 沙发鱼霸API文档

# 阅前必看

## 目录

> [首页](https://github.com/waitforu/docs/blob/master/index/index.md)
> [发送短信](https://github.com/waitforu/docs/blob/master/send_sms.md)

## 公共信息

| 名称 | 描述 | 备注 |
| ---- | ---- | ---- |
| in | 字段所在位置 |  |
| header | 在头部 |  |
| params | 在衔接在链接上 |

### 公共头

####  api-version
```
type: string
require: true
default: v1
in: header
```
#### 

### 部分返回信息code表

| CODE  |    说明      | 备注  |
| ----- |    ----      | ---  |
| 200   | 请求成功     | data部分为返回数据，如果无data说明该请求不需要返回数据 |
| 400   | 请求失败    | message为简略错误信息，data中为详细错误信息 |
| 403   | 请求被拒绝  | 同400 |
| 404   | 请求链接不存在 | 同400 |
| 422   | 请求数据有误 | 同400 |
| 500   | 服务器错误 | 同400 |
