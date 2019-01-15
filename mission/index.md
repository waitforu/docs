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
|  └─info | array | 是 | 任务列表 |
|　　 ├─m_id | int | 是 | 任务编号 |
|　 　├─name | string | 是 | 任务名称 |
|　 　├─detail | string | 是 | 任务描述 |
|　 　├─integration | int | 是 | 可获渔币 |
|　 　├─thumbnail | string | 是 | 缩略图 |
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
    "data": {
        "info": [
            {
                "m_id": 10001,
                "name": "首次充值",
                "detail": "首次充值",
                "integration": 50,
                "thumbnail": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/cz.png",
                "accomplished": false
            },
            {
                "m_id": 10005,
                "name": "邀请好友",
                "detail": "每邀请一位好友奖励",
                "integration": 288,
                "thumbnail": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/yq.png",
                "accomplished": false,
                "node": 4,
                "spacing": 1
            },
            {
                "m_id": 10003,
                "name": "钓鱼超过60条",
                "detail": "每钓到5条鱼奖励80渔币",
                "integration": 80,
                "thumbnail": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/fishing_count.png",
                "accomplished": false,
                "node": 12,
                "spacing": 5
            },
            {
                "m_id": 10004,
                "name": "钓鱼超过22小时",
                "detail": "每钓2小时鱼奖励80渔币",
                "integration": 80,
                "thumbnail": "https://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/default/fshing_time.png",
                "accomplished": false,
                "node": 11,
                "spacing": 2
            }
        ]
    }
}
```