# 绑定手机号
```
接口地址： http://www.gofishfarm.com/binding/phone
请求方式： POST
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| phone | string | 是 | - | 手机号 |
| code | string | 是 | - | 验证码 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
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

### 输入
```
POST http://www.gofishfarm.com/user/login
headers:
	api-version: v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
posts:
	phone: 18288888888
	code: 123456
```
### 输出
```
{
    "code": 403,
    "message": "该手机号已经绑定请选择其他手机号绑定"
}

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