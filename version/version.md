# 获取版本号
```
接口地址： http://www.gofishfarm.com/version/{app_type}
请求方式： GET
接口备注：
```

## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| app-version | string | 是 | params | v0.0.1bate | 客户端APP版本 |
| app_type | int | 是 | params | 1 | APP类型; 1:安卓，2：ios |

## 描述

## 接收参数
无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─version | string | 是 | 最新版本号 |
|　├─update | boolean | 是 | 是否需要更新 |
|　├─enforce | int | 否 | 是否强制更新，1是 |
|　├─link | string | 否 | 新app包地址 |
|　└─description | int | 否 | 版本介绍 |