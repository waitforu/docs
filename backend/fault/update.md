# 故障处理
```
接口地址： http://admin_fnsjs.gofishfarm.com/api/fault/{id}
请求方式： PUT
接口备注： 
```
## 请求参数

| 字段名称 | 字段类型 | 是否必须 | 位置 | 默认值 | 说明 |
|    -    |    -    |    -    |  -   |   -   |  -   |
| api-version | string | 是 | header | v1 | api版本号 |
| Authorization | string | 是 | header | - | 验证令牌 |
| id | int | 是 | params | - | 故障ID |

## 描述

## 接收参数

| 字段名称 | 字段类型 | 是否必须 | 默认值 | 说明 |
|    -    |    -    |    -    |    -   |  -   |
| details | int | 是 | - | 问题编码 |
| solution | string | 否 | - | 详细描述 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 是 | 返回信息集，不存在则无返回信息 |

## 范例

### 输入

```
PUT http://admin_fnsjs.gofishfarm.com/api/fault/5
headers:
	api-version: v1
posts:
	details: 1
	solution: "电机失灵"
```

### 输出
```json
{
    "code": 200,
    "message": "success"
}
或者
{
    "code": 422,
    "message": "故障已修复"
}
```