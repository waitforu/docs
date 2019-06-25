# 进入钓鱼
```
接口地址： http://www.gofishfarm.com/fishing_help
请求方式： POST
接口备注： 
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| type | int | 是 | 2 | 钓台类型, 1 手动钓台，2 自动钓台 |
| fp_id | int | 否 | - | 钓台编号 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　└─tiro_prompt | string | 是 | 帮助内容 |

## 范例

### 发送信息

```
POST http://www.gofishfarm.com/fishing
headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
	Content-Type : application/x-www-form-urlencoded
body:
	type: 2
    fp_id: 7
```

### 回收信息

```
{
    "code": 200,
    "message": "success",
    "data": {
        "tiro_prompt": "重新上饵，按“上饵”；饵团太大、太黏，按“抖饵”；完成上饵，开始钓鱼，按“垂钓”。"
    }
}
或者
{
    "code": 403,
    "message": "钓台未运行"
}
```