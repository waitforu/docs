# 创建订单
```
接口地址： http://www.gofishfarm.com/applepay
请求方式： POST
接口备注： 
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| receipt | string | 是 | - | 苹果支付票据 |
| order_id | string | 是 | - | 平台订单号 |
| transaction_id | string | 是 | - | 苹果订单订单号 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |

## 范例
### 输入

```
POST http://www.gofishfarm.com/applepay

headers:
    api-version:v1
    Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
    Content-Type : application/x-www-form-urlencoded
params:
    receipt:1
    order_id:2019051419035802591044067224273
    transaction_id:1
```

### 输出
```json
{
    "code": 200,
    "message": "success"
}
```