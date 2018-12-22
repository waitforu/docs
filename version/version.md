# 获取版本号
```
接口地址： http://148.70.13.176/version/{app_type}
请求方式： GET
请 求 头: api-version:v1，app-version:v0.0.1bate
请求参数: app_type:{1:安卓，2：ios}
接口备注： api-version为api接口版本号, app-version为客户端APP版本
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
|　├─version | string | 是 | 最新版本号 |
|　├─update | boolean | 是 | 是否需要更新 |
|　├─enforce | int | 否 | 是否强制更新，1是 |
|　├─link | string | 否 | 新app包地址 |
|　└─description | int | 否 | 版本介绍 |