# 注册设备ID
```
接口地址： http://www.gofishfarm.com/register
请求方式： POST
接口备注：
```

## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| imei | string | 是 | - | 手机IMEI码 |
| android_id | int | 否 | 安卓渠道号，和苹果手机型号2个选填一个 |
| ios_type | string | 否 | 苹果手机型号，和安卓渠道号2个选填一个 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─id | int | 是 | 编号 |
|　├─imei | string | 是 | IMEI码 |
|　├─ios_type | string | 否 | 苹果手机类型 |
|　├─android_id | int | 否 | 安卓渠道号 |
|　├─activated_at | int | 是 | 注册时间 |
|　├─associated_at | int | 否 | 关联时间 |
|　└─fisher_id | int | 否 | 关联钓手号 |