# 用户登录
```
接口地址： http://admin_fnsjs.gofishfarm.com/api/login
请求方式： POST
接口备注： 
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| user_name | string | 是 | - | 用户名 |
| password | string | 是 | - | 登陆密码 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　├─access_token | string | 是 | access token |
|　├─expires_time | int | 是 | token过期时间 |
|　├─refresh_token | string | 是 | 刷新access_token的refresh_token |
|　└─client | array | 是 | 用户信息 |
|　 　　├─apikey | string | 是 | api校验值 |
|　 　　├─admin_id | int | 是 | 钓手号 |
|　 　　└─phone | string | 是 | 手机号 |

## 范例

### 输入

```
POST http://admin_fnsjs.gofishfarm.com/api/login
headers:
	api-version: v1
posts:
	user_name: admin
	password: 123456
```

### 输出
```json
{
    "code": 200,
    "message": "success",
    "data": {
        "access_token": "x6UTi29w15YX74LD8rMa7CByGSJeo14z",
        "expires_time": 604800,
        "refresh_token": "OC4p7T9QsJ7d1FW5w5A1qrziv8LlENeG",
        "user": {
            "admin_id": 9999,
            "apikey": "QsFPF59ZVm7MTlOeufQnwBNqHnFWaNcp",
            "phone": null
        }
    }
}
或者
{
    "code": 422,
    "message": "用户名或密码错误"
}
```