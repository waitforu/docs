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
|　└─packages | array | 是 | 套餐列表 |
|　 　　├─package_id | string | 是 | 套餐编号 |
|　 　　├─name | string | 是 | 套餐名称 |
|　 　　├─details | string | 是 | 套餐描述 |
|　 　　├─price | float | 是 | 套餐单价价格 |
|　 　　├─thrift_price | float | 是 | 套餐相对于1小时可节省金额 |
|　 　　├─time | string | 是 | 套餐时长 |
|　 　　└─discount | int | 是 | 套餐折扣 |

## 范例

### 输入
```
GET http://148.70.13.176/times
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
        "packages": [
            {
                "package_id": "20190101",
                "name": "3小时套餐",
                "details": "3h/￥15",
                "price": 15,
                "time": "3h",
                "discount": 100
            },
            {
                "package_id": "20190102",
                "name": "5小时套餐",
                "details": "5h/￥20",
                "price": 20,
                "time": "5h",
                "discount": 100
            }
        ]
    }
}
```