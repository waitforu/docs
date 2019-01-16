# 粉丝页列表
```
接口地址： http://148.70.13.176/fans
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| page | 否 | 是 | params | 1 | 页码 |

## 描述

## 接收参数

无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |
|　├─page | int | 是 | 当前页码 |
|　├─total_page | int | 是 | 总页码 |
|　└─fans | array | 否 | 兑换记录表 |
|　 　　├─fisher_id | int | 是 | 钓手号 |
|　 　　├─status | int | 是 | 钓手在线状态 1 离线，2 在线，3 垂钓中, 4 围观中|
|　 　　├─avatar | string | 是 | 钓手头像地址 |
|　 　　├─mutual_focus | int | 是 | 关注状态，1 未关注, 2 已关注, 3 互相关注 |
|　 　　└─nick_name | int | 是 | 昵称 |

## 范例

### 输入
```
GET http://148.70.13.176/fans

headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
params:
	page: 1
```
### 输出
```
{
    "code": 200,
    "message": "success",
    "data": {
        "fans": [
            {
                "fisher_id": 98045418,
                "status": 2,
                "nick_name": "runmanz",
                "avatar": "https://runmanz-1251536883.cos.ap-shanghai.myqcloud.com/default/itachi.jpg",
                "mutual_focus": 1
            }
        ],
        "page": "1",
        "total_page": 1
    }
}
```