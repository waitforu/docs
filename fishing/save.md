# 进入钓鱼
```
接口地址： http://148.70.13.176/fishing
请求方式： POST
接口备注： 快速开始钓鱼接口不需要传fishery_id, fp_id, 进入渔场进行钓鱼时要带上fishery_id, 进入钓台进行钓鱼是要带上fp_id; status预留前期传1
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
| status | int | 是 | 1 | 识别进入方式1 正式，2 测试 |
| fishery_id | int | 否 | - | 渔场编号 |
| fp_id | int | 否 | - | 钓台编号 |

## 返回参数

| 字段名称 | 字段类型 | 是否必须 | 说明 |
|    -    |    -    |    -    |   -   |
| code | int | 是 | [详情查阅README](https://github.com/waitforu/docs/blob/master/README.md#%E9%83%A8%E5%88%86%E8%BF%94%E5%9B%9E%E4%BF%A1%E6%81%AFcode%E8%A1%A8) |
| message | string | 是 | 返回信息简略说明 |
| data | array | 否 | 返回信息集，不存在则无返回信息 |
|　├─info | int | 是 | **用户跳转 0 不跳转, 1 跳转充值页, 2 跳转新手引导页(预留)** |
|　├─fp_id | int | 是 | 钓台编号 |
|　├─dtu_id | string | 是 | DTU设备ID |
|　├─dtu_apikey | string | 是 | DTU设备api-key |
|　├─on_time | int | 是 | 开响应时间 |
|　├─off_time | int | 是 | 关响应时间 |
|　├─lives | array | 是 | 钓台关联所有直播流地址集 |
|　│　　└─下标 | string | 是 | 直播流地址,第一个地址为默认播放地址 |
|　└─commands | array | 是 | 指令集 |
|　 　　├─on1| string | 是 | 一路开指令binary流经过base64加密 |
|　 　　├─off1 | string | 是 | 一路关指令binary流经过base64加密 |
|　 　　├─on2| string | 是 | 二路开指令binary流经过base64加密 |
|　 　　├─off2 | string | 是 | 二路关指令binary流经过base64加密 |
|　 　　├─on3| string | 是 | 三路开指令binary流经过base64加密 |
|　 　　├─off3 | string | 是 | 三路关指令binary流经过base64加密 |
|　 　　├─on4| string | 是 | 四路开指令binary流经过base64加密 |
|　 　　├─off4 | string | 是 | 四路关指令binary流经过base64加密 |
|　 　　├─on5| string | 是 | 五路开指令binary流经过base64加密 |
|　 　　├─off5 | string | 是 | 五路开指令binary流经过base64加密 |
|　 　　├─on6| string | 是 | 五路开指令binary流经过base64加密 |
|　 　　├─off6 | string | 是 | 五路开指令binary流经过base64加密 |
|　 　　└─alloff | string | 是 | 全关指令binary流经过base64加密 |

## 范例

### 发送信息

```
POST http://148.70.13.176/fishing
headers:
	api-version:v1
	Authorization : Bearer NFVvMTFKRnhyUWlOTlBpeFdHS1JWVmZjbWt6UE5Lbjg6NjcyMjQyNzM6akRXNThFQ2UyRzFyM1FSRlpxZDcwVTg0Njd6aU40b2M=
	Content-Type : application/x-www-form-urlencoded
body:
	status : 2

```

### 回收信息

```
{
    "code": 200,
    "message": "success",
    "data": {
        "info": 0,
        "fp_id": 1,
        "dtu_id": "505437446",
        "dtu_apikay": "vAcBwxQ5D4HiISRtxDwoQXxE=xI=",
        "on_time": 300,
        "off_time": 300,
        "lives": [
            "rtmp://dytl.game.caizs.com/live/11111?bizid=37147&txSecret=4bd09fe542ddecc1d0ae42694b6ccb5f&txTime=5C320520"
        ],
        "commands": {
            "on1": "/gUAAP8AmDU=",
            "off1": "/gUAAAAA2cU=",
            "on2": "/gUAAf8AyfU=",
            "off2": "/gUAAQAAiAU=",
            "on3": "/gUAAv8AOfU=",
            "off3": "/gUAAgAAeAU=",
            "on4": "/gUAA/8AaDU=",
            "off4": "/gUAAwAAKcU=",
            "on5": "/gUABP8A2fQ=",
            "off5": "/gUABAAAmAQ=",
            "on6": "/gUABf8AiDQ=",
            "off6": "/gUABQAAycQ=",
            "alloff": "/g8AAAAFAQAgUg=="
        }
    }
}
或者
{
    "code": 200,
    "message": "您的剩余时长不足，请先充值！",
    "data": {
        "info": 1,
    }
}
```