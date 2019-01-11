# 充值记录
```
接口地址： http://148.70.13.176/orders
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
|　└─info | array | 否 | 第N个订单 |
|　 　　├─order_id | string | 是 | 订单号 |
|　 　　├─buy_time | string | 是 | 总购买时长 |
|　 　　├─buy_at | string | 是 | 购买时间 |
|　 　　├─status | string | 是 | 购买状态 |
|　 　　└─price | string | 是 | 总价格 |

## 范例

### 输入

```
GET http://148.70.13.176/orders

headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
```

### 输出

```
{
    "code": 200,
    "message": "success",
    "data": {
        "info": [
            {
                "order_id": "2019010218021701878365067224273",
                "buy_time": "5h",
                "buy_at": "您还未付款",
                "status": "待支付",
                "price": "20.00元"
            }
        ]
    }
}
```