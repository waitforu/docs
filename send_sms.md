# 发送短信接口
```
接口地址： http://148.70.13.176/send_sms
请求方式： POST
请 求 头: api-version:v1 
接口备注： api-version为api接口版本号
```
## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| phone | string | 是 | - | 手机号(必须是大陆手机号) |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md) |
| message | string | 是 | 返回信息简略说明 |