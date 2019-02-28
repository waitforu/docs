# 故障问题
```
接口地址： http://admin_fnsjs.gofishfarm.com/api/fault/create
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
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　└─details | array | 是 | 问题内容，选择框，key为问题编号，value为名称 |

## 待处理页
### 输入
```
GET http://admin_fnsjs.gofishfarm.com/api/fault/create

headers:
	api-version:v1
	Authorization : Bearer cE96R1JRcjhhTHV5bXNzR2xEaWtWYWlYbWVwOHdIYjk6OTk5OTp4ajdUZjZxQTF5Mjg0bTNYb2FSTDlVSlNLclpkenVPZw==
```

### 输出
```json
{
    "code": 200,
    "message": "success",
    "data": {
        "details": [
            {
                "id": 1,
                "name": "鱼线缠绕"
            },
            {
                "id": 2,
                "name": "操作不熟"
            },
            {
                "id": 3,
                "name": "操作失灵"
            },
            {
                "id": 4,
                "name": "其他问题"
            }
        ]
    }
}
```