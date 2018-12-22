# 关注列表
```
接口地址： http://148.70.13.176/focuss
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| page | int | 是 | params | 1 | 页码 |
| pageSize | int | 是 | params | 15| 单页条数 |
| fields | string | 是 | params | - | 搜索条件 |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　└─focus | array | 否 | 兑换记录表 |
|　 　　├─fisher_id | int | 是 | 钓手号 |
|　 　　├─status | int | 是 | 钓手在线状态 |
|　 　　├─avatar | int | 是 | 钓手头像地址 |
|　 　　└─nick_name | int | 是 | 昵称 |