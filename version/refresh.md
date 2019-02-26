# 刷新accessToken
```
接口地址： http://www.gofishfarm.com/refresh/{refresh_token}/{apikey}
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| refresh_token | string | 是 | params | - | 刷新token |
| apikey | string | 是 | params | - | api令牌 |

## 描述

## 接收参数
无

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
|　 　　├─fisher_id | int | 是 | 钓手号 |
|　 　　├─phone | string | 是 | 手机号 |
|　 　　└─invite_token | string | 是 | 邀请码 |