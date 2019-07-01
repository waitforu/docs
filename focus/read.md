# 查看是否已关注该钓手
```
接口地址： http://www.gofishfarm.com/focuss/{$id}
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
|　├─fisher_id | int | 是 | 钓手号 |
|　├─nick_name | string | 是 | 昵称 |
|　├─avatar | int | 是 | 钓手头像地址 |
|　├─rank | string | 是 | 榜单排名 |
|　├─fishery_name | string | 是 | 渔场名称 |
|　└─focused | int | 是 | 关注 1 未关注, 2 已关注, 3 互相关注 |

## 范例

### 请求信息
```
GET http://www.gofishfarm.com/focuss/59041581
headers
	api-version: v1
	Authorization: Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
```

### 返回信息
```
{
    "code": 200,
    "message": "success",
    "data": {
        "fisher_id": 13164844,
        "avatar": "http://sfyb-1258095529.cos.ap-chengdu.myqcloud.com/avatar/1547614250661head.png",
        "nick_name": "钱塘一哥",
        "focused": 1,
        "rank": "第3",
        "fishery_name": "1号钓台"
    }
}
```