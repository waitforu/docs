# 首页信息列表
```
接口地址： http://148.70.13.176/index
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |

## 描述

## 接收参数
无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─banners | array | 否 | banner图数据集，不存在则无banner图 |
|　│　　├─name | string | 是 | banner名称 |
|　│　　├─link | string | 否 | banner关联链接，不存在则无外链 |
|　│　　└─thumbnail | string | 是 | banner图片地址 |
|　└─fisheries | array | 否 | 渔场信息集 |
|　 　　├─fishery_id | int | 是 | 渔场编号 |
|　 　　├─name | string | 是 | 渔场名称 |
|　 　　├─thumbnail | string | 是 | 渔场缩略图 |
|　 　　├─current_capacity | int | 是 | 渔场使用中钓台数 |
|　 　　├─capacity | int | 是 | 渔场总钓台数 |
|　 　　├─surplus_capacity | int | 是 | 渔场空闲钓台数 |
|　 　　├─onlook | int | 是 | 渔场围观人数 |
|　 　　└─details | string | 是 | 渔场描述 |