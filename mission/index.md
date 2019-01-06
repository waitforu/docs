# 我的时长
```
接口地址： http://148.70.13.176/missions
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
|  └─下标 | array | 是 | 任务列表 |
|　　 ├─m_id | int | 是 | 任务编号 |
|　 　├─name | string | 是 | 任务名称 |
|　 　├─detail | string | 是 | 任务描述 |
|　 　├─integration | int | 是 | 可获积分 |
|　 　├─spacing | int | 是 | 级距 |
|　 　├─node | int | 是 | 节点 |
|　 　└─accomplished | boolean | 是 | 是否已完成, true 已完成, false 未完成 |

## 范例

### 输入
```
GET http://148.70.13.176/missions
headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
```

###  输出
```
{
    "code": 200,
    "message": "success",
    "data": [
        {
            "m_id": 10001,
            "name": "首次充值",
            "detail": "首次充值",
            "integration": 1000,
            "accomplished": false
        },
        {
            "m_id": 10002,
            "name": "第一次钓到鱼",
            "detail": "第一次钓到鱼",
            "integration": 3000,
            "accomplished": false
        },
        {
            "m_id": 10003,
            "name": "钓到10条鱼",
            "detail": "每钓到10条鱼奖励2000积分",
            "integration": 2000,
            "accomplished": false,
            "node": 1,
            "spacing": 10
        }
    ]
}
```