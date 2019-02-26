# 时长记录
```
接口地址： http://www.gofishfarm.com/times/{fisher_id}
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| fisher_id | int | 是 | params | - | 钓手号 |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　└─list | array | 否 | 兑换记录表 |
|　 　　├─title | string | 是 | 时长记录标题 |
|　 　　├─times | string | 是 | 时长 |
|　 　　└─created_at | string | 是 | 记录时间 |


## 范例

### 输入
```
GET http://www.gofishfarm.com/times/67224273

headers:
    api-version:v1
    Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
```
### 输出

```json
{
    "code": 200,
    "message": "success",
    "data": {
        "list": [
            {
                "times": "-0.1h",
                "title": "钓鱼使用时长",
                "created_at": "2019-01-21 13:41:59 ~ 1970-01-01 08:00:01"
            },
            {
                "times": "+1h",
                "title": "花费400渔币兑换时长",
                "created_at": "2019-01-17 18:06:11"
            },
            {
                "times": "+1h",
                "title": "花费6.4元购买时长",
                "created_at": "2019-01-16 12:58:58"
            },
            {
                "times": "+1h",
                "title": "花费1000渔币兑换时长",
                "created_at": "2018-12-22 16:06:54"
            },
            {
                "times": "+1h",
                "title": "花费1000渔币兑换时长",
                "created_at": "2018-12-12 15:28:36"
            },
            {
                "times": "+5h",
                "title": "注册赠送时长",
                "created_at": "1970-01-01 08:00:00"
            }
        ]
    }
}
```