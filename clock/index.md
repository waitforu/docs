# 签到首页/今日是否以前的
```
接口地址： http://148.70.13.176/clocks
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
|　├─clock_setting | array | 是 | 连续签到N天可获渔币列表 |
|　│　　└─下标N | int | 是 | 连续N+1天可获渔币<br/>例：[0 => 1]表示连续签到1天可获1渔币, <br/>[2 => 2]连续签到3天可获2渔币 |
|　├─continuous_times | int | 是 | 已经连续签到天数 |
|　└─hasClocked | boolean | 是 | 今日是否已签到 |

## 范例

### 输入
```
GET http://148.70.13.176/clocks

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
        "clock_setting": [
            1,
            1,
            1,
            2,
            2,
            2,
            3
        ],
        "hasClocked": false,
        "continuous_times": 0
    }
}
```