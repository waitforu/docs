# 获取累计钓鱼数榜单
```
接口地址： http://148.70.13.176/ranks
请求方式： GET
请 求 头: api-version:v1
接口备注： api-version为api接口版本号
```
## 描述

## 接收参数
无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　└─数组下标| array | 无 |  |  
|　 　　├─fisher_id | int | 是 | 钓手号 |
|　 　　├─nick_name | string | 是 | 钓手昵称 |
|　 　　├─avatar | string | 是 | 钓手头像地址 |
|　 　　├─total_fishing | int | 是 | 累计钓鱼数 |
|　 　　└─status | int | 是 | 在线状态 |