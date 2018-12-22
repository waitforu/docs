# 我的时长
```
接口地址： http://148.70.13.176/times
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
|　├─time | float | 是 | 剩余时长 |
|　├─integration | Boolean | 是 | 积分是否足够兑换 |
|　├─clocked | boolean | 是 | 今天是否已签到 |
|　└─mission | array | 否 | 任务列表 |
|　 　　└─m_id | int | 是 | 任务编号 |
|　 　　 　├─name | string | 是 | 任务名称 |
|　 　　 　├─detail | string | 是 | 任务描述 |
|　 　　 　├─integration | int | 是 | 可获积分 |
|　 　　 　├─spacing | int | 是 | 级距 |
|　 　　 　├─node | int | 是 | 节点 |
|　 　　 　└─accomplished | boolean | 是 | 是否已完成 |