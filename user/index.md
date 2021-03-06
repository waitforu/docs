# 个人中心
```
接口地址： http://www.gofishfarm.com/users
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
|　├─fisher_id | int | 是 | 钓手号 |
|　├─nick_name | string | 是 | 昵称 |
|　├─avatar | string | 是 | 头像地址 |
|　├─phone | string | 是 | 手机号 |
|　├─sex | int | 是 | 性别，1 男，2 女 |
|　├─sex_zh | string | 是 | 性别中文 |
|　├─total_fishing | int | 是 | 总钓鱼数 |
|　├─likes | int | 是 | 点赞数 |
|　├─focus | int | 是 | 关注数 |
|　├─fans | int | 是 | 粉丝数 |
|　└─remaining_time | float | 是 | 剩余钓鱼时长/单位h |
## 范例

### 输入
```
GET http://www.gofishfarm.com/users

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
        "fisher_id": "67224273",
        "nick_name": "runmanz",
        "avatar": "https://runmanz-1251536883.cos.ap-shanghai.myqcloud.com/default/itachi.jpg",
        "phone": "28267857539",
        "sex": 1,
        "sex_zh": "男",
        "total_fishing": 15,
        "likes": 19,
        "focus": 3,
        "fans": 2,
        "remaining_time": 52.98
    }
}
```