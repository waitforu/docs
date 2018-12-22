# 个人信息
```
接口地址： http://148.70.13.176/users/{fisher_id}/edit
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| fisher_id | int | 是 | params | - | 钓手号 |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　├─nick_name | string | 是 | 昵称 |
|　├─avatar | string | 是 | 头像地址 |
|　├─phone | string | 是 | 手机号 |
|　├─sex | int | 是 | 性别，1 男，2 女 |
|　├─sex_zh | string | 是 | 性别中文 |
|　├─wechat_on | boolean | 是 | 是否已绑定微信 |
|　├─weibo_on | boolean | 是 | 是否已绑定微博 |
|　├─birthday | int | 是 | 生日时间戳 |
|　├─birthday_ymd | string | 是 | 生日 |
|　├─city | int | 是 | 城市编号 |
|　├─city_zh | string | 是 | 城市名称 |
|　└─fishing_age | float | 是 | 钓龄 |