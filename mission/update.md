# 领取奖励
```
接口地址： http://148.70.13.176/missions/{$m_id}
请求方式： PUT
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| m_id | string | 是 | params | - | 任务编号 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| node | string | 否 | - | 阶梯级别。 没有可以不用填; 当页面数据存在node时, 必须带上node |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|  └─info | int | 是 | 跳转链接 0 不跳转, 1 跳转充值页, 2 跳转邀请好友页 |


## 范例

### 输入
```
PUT http://148.70.13.176/missions/10001

headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
body:
	node: 0 // 没有可以不用填, 当页面数据存在node时, 必须带上node
```
### 输出
```
{
    "code": 200,
    "message": "success",
    "data": {
        "info": 0
    }
}

或者

{
    "code": 403,
    "message": "任务领取失败",
    "data": {
        "info": 0
    }
}
或者
{
    "code": 408,
    "message": "请求超时",
    "data": {
        "info": 0
    }
}
或者
{
    "code": 200,
    "message": "您还未进行首次充值请充值后再领取奖励",
    "data": {
        "info": 1
    }
}
```