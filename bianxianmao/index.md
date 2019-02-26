# 获取变现猫
```
接口地址： http://www.gofishfarm.com/bianxianmao
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
|　└─url | string | 是 | 变现猫免登录URL |

# 注意事项
**url中需严格与范例中的链接内容格式一致，使用时不能再次urldecode或者urlencode**

## 范例

### 输入
```
GET http://www.gofishfarm.com/bianxianmao

headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
```
### 输出
```
{
    "code": 200,
    "message": "success",
    "data": {
        "url": "https://jifen.bianxianmao.com?appKey=a815f23552284d5aa5e03a68ecdd158d&appType=app&appUid=67224273&timestamp=1548312507415&nickName=runmanz&face=https%3A%2F%2Frunmanz-1251536883.cos.ap-shanghai.myqcloud.com%2Fdefault%2Fitachi.jpg&sign=38a3cd9a0d37ecfecfe4e83165982c08"
    }
}
```