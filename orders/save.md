# 创建订单
```
接口地址： http://www.gofishfarm.com/orders
请求方式： POST
接口备注： 微信appid和商户号从app本地获取
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
| package_id | string | 是 | - | 套餐编号 |
| pay_way | int | 是 | 1 | 支付方式 1 支付宝, 2 微信 |
| number | int | 是 | 1 | 购买数量 |

## 返回参数

> type = 1 支付宝支付

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　└─orderInfo | string | 是 | alipay请求字符串 |

> type = 2 微信支付

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─prepayid | string | 是 | 微信返回的支付交易会话ID |
|　├─package_str | string | 是 | 扩展字段, 暂填写固定值Sign=WXPay |
|　├─noncestr | string | 是 | 随机字符串 |
|　├─timestamp | int | 是 | 时间戳 |
|　└─sign | string | 是 | 签名 |

> type = 3 苹果支付

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─prepayid | string | 是 | 微信返回的支付交易会话ID |
|　├─package_str | string | 是 | 扩展字段, 暂填写固定值Sign=WXPay |
|　├─noncestr | string | 是 | 随机字符串 |
|　├─timestamp | int | 是 | 时间戳 |
|　└─sign | string | 是 | 签名 |


## 范例

> type = 1

### 输入

```
POST http://www.gofishfarm.com/orders

headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
	Content-Type : application/x-www-form-urlencoded
params:
	package_id: 20190102
	pay_way: 1
	number: 1
```

### 输出

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "orderInfo": "alipay_sdk=alipay-sdk-php-20180705&app_id=2018121862595325&biz_content=%7B%22subject%22%3A%22%5Cu6c99%5Cu53d1%5Cu6e14%5Cu9738-5%5Cu5c0f%5Cu65f6%5Cu5957%5Cu9910%22%2C%22out_trade_no%22%3A%222019011018452401262919067224273%22%2C%22total_amount%22%3A20%2C%22timeout_express%22%3A%2230m%22%2C%22product_code%22%3A%22QUICK_MSECURITY_PAY%22%7D&charset=UTF-8&format=json&method=alipay.trade.app.pay&notify_url=http%3A%2F%2Fwww.gofishfarm.com%2Falipay&sign_type=RSA2&timestamp=2019-01-10+18%3A45%3A25&version=1.0&sign=ibgHgpeCcpMh8UJRoM5Q6US0ZlwzzxaK1A2MO%2FjfnQhhgN8CCXiXyJ1biDUPsj%2ByxbQ3nVr9g916QTddRJsTeAg0F3ZJ0WK4SIU8i9cpnfRqBRBxiMpRlvQa0EFqF2Bx8XFkQNsDC3Gtgz05DtCk7rmwlhfVF094jjlVjaupRllBvJuy%2F6o56ImelThur3rzBJ0u1eKYJnmUG5LqS4QXmvZDuixmP1ML1wo1BEB4P0yhoNAyC6F1xqhWxn8YQOXkd%2Fp%2BHlQiwbbUF2RUW2otfKaz2YAS0tw%2Bspqwq4dDR6WK0caVHbZ3dEuapDHBv%2F4mp9d0M4P4%2F2aSnZ5BxFaMEw%3D%3D"
    }
}
```

> type = 2

### 输入

```
POST http://www.gofishfarm.com/orders

headers:
    api-version:v1
    Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
    Content-Type : application/x-www-form-urlencoded
params:
    package_id: 20190102
    pay_way: 2
    number: 1
```

### 输出
```json
{
    "code": 200,
    "message": "success",
    "data": {
        "prepayid": "wx101015191124682873bb11140792662597",
        "package_str": "Sign=WXPay",
        "noncestr": "unRvmYCFOZaheyZH",
        "timestamp": 1547086519,
        "sign": "1787A47A0B5D888EE0315F411DFFF71198BE0ECFB06BDC3876FE995F13ADC972"
    }
}
```

> type = 3

### 输入

```
POST http://www.gofishfarm.com/orders

headers:
    api-version:v1
    Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
    Content-Type : application/x-www-form-urlencoded
params:
    package_id: iap00001
    pay_way: 3
    number: 1
```

### 输出
```json
{
    "code": 200,
    "message": "success",
    "data": {
        "order_id": "2019051416423002540877067224273",
        "phone": "18267857539",
        "buyer": "67224273",
        "total_pay": 12,
        "buy_time": 3600
    }
}
```
