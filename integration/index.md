# 渔币兑换记录
```
接口地址： http://www.gofishfarm.com/integrations
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
|　└─list | array | 否 | 兑换记录表 |
|　 　　├─title | string | 是 | 渔币记录标题 |
|　 　　├─integration | int | 是 | 渔币 |
|　 　　└─created_at | int | 是 | 记录时间 |


## 范例

### 输入
```
GET http://www.gofishfarm.com/integrations

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
        "list": [
            {
                "title": "兑换了1h*1",
                "integration": "-400渔币",
                "created_at": "2019-01-17 18:06:11"
            },
            {
                "title": "钓鱼超过5条奖励",
                "integration": "+80渔币",
                "created_at": "2019-01-17 17:02:38"
            },
            {
                "title": "邀请了3个好友奖励",
                "integration": "+864渔币",
                "created_at": "2019-01-17 17:01:33"
            },
            {
                "title": "邀请了3个好友奖励",
                "integration": "+864渔币",
                "created_at": "2019-01-17 17:00:12"
            }
        ]
    }
}
```