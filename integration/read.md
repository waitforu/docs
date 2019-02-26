# 我的渔币
```
接口地址： http://www.gofishfarm.com/integrations/{fisher_id}
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
|　├─available_integration | int | 是 | 可用渔币 |
|　├─total_integration | string | 是 | 总渔币 |
|　├─total_fishing | string | 是 | 累计钓鱼数 |
|　└─settings | array | 是 | 渔币兑换列表 |
|　 　　├─is_id | int | 是 | 兑换编号 |
|　 　　├─integration | int | 是 | 所需渔币 |
|　 　　├─time | int | 是 | 可兑换时长 |
|　 　　└─description | string | 是 | 兑换项描述 |