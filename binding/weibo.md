# 绑定/取绑微博
```
接口地址： http://148.70.13.176/binding/weibo
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
| type | int | 是 | 1 | 绑定类型 1 解绑, 2 绑定 |
| weibo_id | string | 否 | - | 微博标识码, 绑定时必带 |
| nick_name | string | 否 | - | 微博昵称, 绑定时必带 |
| avatar | string | 否 | - | 微博头像, 绑定时必带 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |

## 范例

### 输入
```
POST http://148.70.13.176/binding/weibo
headers:
	api-version: v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
posts:
	type: 2
	weibo_id: oNr9b1ApMwbWXESKOArfs4BO5mXc
    nick_name: Murning
    avatar: http://thirdwx.qlogo.cn/mmopen/vi_32/DYAIOgq83erNRxoUDtJJgan8Tb41Lj7qtHrSibFxZ9vlf529Pibic3g8D64TJMGlzFlQtQYeKK0znu64ic5eA4SFvw/132
```
### 输出
```
{
    "code": 403,
    "message": "您未绑定微博"
}
或者
{
    "code": 200,
    "message": "success"
}

```