# 渔币兑换记录
```
接口地址： http://148.70.13.176/integrations
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　└─list | array | 否 | 兑换记录表 |
|　 　　├─iu_id | string | 是 | 兑换单号 |
|　 　　├─time | int | 是 | 兑换获得单位时长 |
|　 　　├─number | int | 是 | 兑换数量 |
|　 　　├─integration | int | 是 | 兑换使用渔币 |
|　 　　└─created_at | int | 是 | 兑换时间 |