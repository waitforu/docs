# 首页及全部信息
```
接口地址： http://admin_fnsjs.gofishfarm.com/api/index
请求方式： GET
接口备注：
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| status | int | 是 | params | 1 | 页面状态，1 待处理页，2 全部页 |
| fault_status | int | 否 | params | - | 处理状态 1 待处理，2 已处理 |
| fishery_id | int | 否 | params | - | 渔场编号 |
| time | int | 否 | params | - | 查询时间范围 |
| page | int | 否 | params | - | 当前页码 |

## 描述

## 接收参数
无

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─list | array | 否 | 故障列表，为null时表示不存在故障信息 |
|　│　　├─id | int | 是 | 故障编号——进入操作故障时的ID |
|　│　　├─reported_at | string | 否 | 上报故障时间 |
|　│　　├─fp_id | string | 否 | 钓台编号 |
|　│　　├─name | string | 否 | 钓场名称 |
|　│　　├─status | string | 是 | 状态 |
|　│　　├─solved_at | string | 否 | 处理时间 |
|　│　　└─des | string | 是 | 故障描述 |
|　├─page | int | 否 | 当前页码——待处理没有该信息 |
|　├─total | int | 否 | 全部条目——待处理没有该信息 |
|　└─fields | array | 是 | 全部页搜索条件 |
|　 　　├─fisheries | array | 是 | 渔场细信息，key为渔场ID，value为渔场名称 |
|　 　　├─time | array | 是 | 时间条件，key为搜索键值，value为key代表的内容 |
|　 　　└─fault_status | string | 是 | 处理状，key为键值，value为key代表的内容 |

## 待处理页
### 输入
```
GET http://admin_fnsjs.gofishfarm.com/api/index

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
        "list": [
            {
                "id": 6,
                "reported_at": "02.27 16:00:14",
                "fp_id": 5,
                "name": "测试渔场",
                "status": "待处理",
                "des": "操作故障"
            }
        ],
        "fields": {
            "fisheries": [
                {
                    "fishery_id": 5,
                    "name": "测试渔场"
                },
                {
                    "fishery_id": 6,
                    "name": "单片机测试"
                }
            ],
            "time": [
                {
                    "id": 1,
                    "name": "近1天"
                },
                {
                    "id": 2,
                    "name": "近3天"
                },
                {
                    "id": 3,
                    "name": "近7天"
                },
                {
                    "id": 4,
                    "name": "近半月"
                },
                {
                    "id": 5,
                    "name": "近一月"
                }
            ],
            "fault_status": [
                {
                    "id": 1,
                    "name": "待处理"
                },
                {
                    "id": 2,
                    "name": "已处理"
                }
            ]
        }
    }
}
```

## 全部页

### 输入
```
GET http://admin_fnsjs.gofishfarm.com/api/index?status=2&time=5&fault_status=1&fishery_id=5

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
        "list": [
            {
                "id": 6,
                "reported_at": "02.27 16:00:14",
                "fp_id": 5,
                "name": "测试渔场",
                "status": "已处理",
                "solved_at": "02.27 16:00:14",
                "des": "操作故障"
            }
        ],
        "page": 1,
        "total": 1,
        "fields": {
            "fisheries": [
                {
                    "fishery_id": 5,
                    "name": "测试渔场"
                },
                {
                    "fishery_id": 6,
                    "name": "单片机测试"
                }
            ],
            "time": [
                {
                    "id": 1,
                    "name": "近1天"
                },
                {
                    "id": 2,
                    "name": "近3天"
                },
                {
                    "id": 3,
                    "name": "近7天"
                },
                {
                    "id": 4,
                    "name": "近半月"
                },
                {
                    "id": 5,
                    "name": "近一月"
                }
            ],
            "fault_status": [
                {
                    "id": 1,
                    "name": "待处理"
                },
                {
                    "id": 2,
                    "name": "已处理"
                }
            ]
        }
    }
}
```