# 用户登录
```
接口地址： http://www.gofishfarm.com/user/login
请求方式： POST
接口备注： 
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |

## 描述

## 接收参数 —— 手机登录

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| phone | string | 是 | - | 手机号(必须是大陆手机号) |
| code | string | 是 | - | 短信验证码 |
| imei | string | 是 | - | IMEI码 |

## 接收参数 —— 微信登录

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| wechat_id | string | 是 | - | 微信唯一标识码 |
| nick_name | string | 是 | - | 微信昵称 |
| avatar | string | 是 | - | 微信头像地址 |
| gender | string | 是 | 1 | 性别1 男，2 女 |
| imei | string | 是 | - | IMEI码 |

## 接收参数 —— 微博登录

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| weibo_id | string | 是 | - | 微博唯一标识码 |
| nick_name | string | 是 | - | 微博昵称 |
| avatar | string | 是 | - | 微博头像地址 |
| gender | string | 是 | 1 | 性别1 男，2 女 |
| imei | string | 是 | - | IMEI码 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　├─access_token | string | 是 | access token |
|　├─expires_time | int | 是 | token过期时间 |
|　├─refresh_token | string | 是 | 刷新access_token的refresh_token |
|　├─locked | boolean | 是 | 是否已经绑定手机号, true 是, false否 |
|　└─client | array | 是 | 用户信息 |
|　 　　├─apikey | string | 是 | api校验值 |
|　 　　├─fisher_id | int | 是 | 钓手号 |
|　 　　├─phone | string | 是 | 手机号 |
|　 　　└─invite_token | string | 是 | 邀请码 |

## 范例

### 输入1

```
POST http://www.gofishfarm.com/user/login
headers:
	api-version: v1
posts:
	phone: 18288888888
	code: 123456
	imei: 865441030309330
```

### 输入2
```
POST http://www.gofishfarm.com/user/login
headers:
	api-version: v1
posts:
	wechat_id: 11111123
	nick_name: Murning
	avatar: https://runmanz-1251536883.cos.ap-shanghai.myqcloud.com/default/itachi.jpg
	gender: 1
	imei: 865441030309330
```

### 输入3
```
POST http://www.gofishfarm.com/user/login
headers:
	api-version: v1
posts:
	weibo_id: asdasgdafeasd
	nick_name: Murning
	avatar: https://runmanz-1251536883.cos.ap-shanghai.myqcloud.com/default/itachi.jpg
	gender: 1
	imei: 865441030309330
```

### 输出
```json
{
    "code": 200,
    "message": "success",
    "data": {
        "access_token": "gc4d8zTMR5Br1wXJ09356VqPLmZQOptA",
        "expires_time": 604800,
        "refresh_token": "fqM5n0Q46IrLu51z2sJ8wpB3a4ltTNXh",
        "locked": true,
        "user": {
            "fisher_id": 67224273,
            "apikey": "mKm3pTXSZtwAi2HVj0GhiAFHYcG6XOms",
            "phone": "18267857539",
            "invite_token": "b4paLVLjGzM8rta6p0bJDbXsLcOzxMp3"
        }
    }
}
```