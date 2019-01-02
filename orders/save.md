# 创建订单
```
接口地址： http://148.70.13.176/orders
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
| package_id | string | 是 | - | 套餐编号 |
| pay_way | int | 是 | 1 | 支付方式 |
| number | int | 是 | 1 | 购买数量 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─order_id | string | 是 | 订单号 |
|　├─phone | string | 是 | 总积分 |
|　├─buyer | int | 是 | 钓手号 |
|　├─buy_time | int | 是 | 购买总时长 |
|　├─price | float | 是 | 总价格 |
|　└─items | array | 是 | 订单副表 |
|　 　　├─package_id | string | 是 | 套餐编号 |
|　 　　├─pack_name | string | 是 | 套餐名称 |
|　 　　├─pack_time | int | 是 | 套餐单位时长 |
|　 　　├─price | float | 是 | 套餐单价 |
|　 　　└─number | int | 是 | 购买数量 |

## 范例

### 输入

```
POST http://148.70.13.176/orders

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

```
{
    "code": 200,
    "message": "success",
    "data": {
        "order_id": "2019010218021701878365067224273",
        "phone": "18267857539",
        "buyer": "67224273",
        "buy_time": 5,
        "price": 20,
        "items": {
            "package_id": "20190102",
            "pack_name": "5小时套餐",
            "pack_time": 5,
            "price": 20,
            "number": "1"
        }
    }
}
```