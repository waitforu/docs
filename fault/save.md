# 用户报障
```
接口地址： http://www.gofishfarm.com/notices
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
| fp_id | int | 是 | - | 钓台编号 |
| type | int | 是 | - | 故障类型 |
| solution | string | 否 | - | 详细描述 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |

## 范例

### 发送信息

```
POST http://www.gofishfarm.com/notices
headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
	Content-Type : application/x-www-form-urlencoded
body:
	fp_id: 5
	type: 5
	solution: '16:12分记鱼器少记一条鱼'

```

### 回收信息

```
{
    "code": 200,
    "message": "success"
}
或者
缺少fp_id时
{
    "code": 422,
    "message": "错误的报障方式"
}
缺少type时
{
    "code": 422,
    "message": "请输入正确的故障类型"
}
```