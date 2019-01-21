# 围观接口
```
接口地址： http://148.70.13.176/onlooks
请求方式： POST
接口备注： 前去围观接口不需要传fishery_id, field, 进入钓台已满的渔场进行围观时要带上fishery_id, 在围观页面搜索钓手号或手机号时要带上field;
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
| fishery_id | string | 否 | - | 渔场编号 |
| field | string | 否 | - | 钓手号或者手机号 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─fp_id | int | 是 | 钓台编号 |
|　├─lives | string | 是 | 围观地址 |
|　└─fishing_fisher | array | 是 | 钓鱼者信息 |
|　　 ├─nick_name | string | 是 | 昵称 |
|　 　├─avatar | string | 是 | 头像 |
|　 　├─fisher_id | int | 是 | 钓手号 |
|　 　└─focus_status | int | 是 | 关注状态，1 未关注, 2 已关注, 3 互相关注 |

## 范例

### 发送信息

```
POST http://148.70.13.176/onlooks
headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
body:
	fishery_id : 123

```

### 回收信息

```
{
    "code": 200,
    "message": "success",
    "data": {
        "fp_id": 1
        "lives": "rtmp://play.gofishfarm.com/live/11111",
        "fishing_fisher": {
            "nick_name": "runmanz",
            "avatar": "https://runmanz-1251536883.cos.ap-shanghai.myqcloud.com/default/itachi.jpg",
            "fisher_id": 67224273,
            "focus_status": 1
        }
    }
}
或者
{
    "code": 403,
    "message": "还未有人开始钓鱼，请稍候来看"
}
```