# 我的时长
```
接口地址： http://148.70.13.176/times
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| app_type | string | 否 | param | android | 对应APP类型，安卓：android，iOS：ios |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　├─time | float | 是 | 剩余时长 |
|　├─discount | string | 是 | 优惠优惠 空字符串没有首充优惠，'八'有 |
|　└─packages | array | 是 | 套餐列表 |
|　 　　├─package_id | string | 是 | 套餐编号/iOS对应产品ID |
|　 　　├─name | string | 是 | 套餐名称 |
|　 　　├─details | string | 是 | 套餐描述 |
|　 　　├─price | float | 是 | 套餐单价价格 |
|　 　　├─thrift_price | float | 是 | 套餐相对于1小时可节省金额 |
|　 　　├─time | string | 是 | 套餐时长 |
|　 　　└─discount | int | 是 | 套餐折扣 |

## 范例

### 苹果输入
```
GET http://dev-api.gofishfarm.com/times
headers:
    api-version:v1
    Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
params:
    app_type: ios
```
### 输出
```
{
    "code": 200,
    "message": "success",
    "data": {
        "time": 58.98,
        "discount": "",
        "packages": [
            {
                "package_id": "iap00001",
                "name": "1小时套餐",
                "details": "1h/￥12",
                "price": 12,
                "time": 1,
                "discount": 100,
                "thrift_price": 0
            },
            {
                "package_id": "iap00002",
                "name": "3小时套餐",
                "details": "3h/￥30",
                "price": 30,
                "time": 3,
                "discount": 100,
                "thrift_price": 6
            },
            {
                "package_id": "iap00003",
                "name": "5小时套餐",
                "details": "5h/￥50",
                "price": 50,
                "time": 5,
                "discount": 100,
                "thrift_price": 10
            },
            {
                "package_id": "iap00004",
                "name": "10小时套餐",
                "details": "10h/￥88",
                "price": 88,
                "time": 10,
                "discount": 100,
                "thrift_price": 32
            }
        ]
    }
}
```

### 输入
```
GET http://dev-api.gofishfarm.com/times
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
        "time": 0,
        "discount": "八",
        "packages": [
            {
                "package_id": "20190101",
                "name": "1小时套餐",
                "details": "1h/￥8",
                "price": 6.4,
                "time": 1,
                "discount": 100,
                "thrift_price": 1.6
            },
            {
                "package_id": "20190102",
                "name": "3小时套餐",
                "details": "3h/￥20",
                "price": 16,
                "time": 3,
                "discount": 100,
                "thrift_price": 8
            },
            {
                "package_id": "20190114",
                "name": "5小时套餐",
                "details": "5h/￥32",
                "price": 25.6,
                "time": 5,
                "discount": 100,
                "thrift_price": 14.4
            },
            {
                "package_id": "20190115",
                "name": "10小时套餐",
                "details": "10h/￥60",
                "price": 48,
                "time": 10,
                "discount": 100,
                "thrift_price": 32
            }
        ]
    }
}
```