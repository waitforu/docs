# 操作解决
```
接口地址： http://admin_fnsjs.gofishfarm.com/api/fault/{id}
请求方式： GET
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
无

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
|　├─fish_integration | int | 是 | 每条鱼对应可获渔币 |
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
|　 　　└─off6 | string | 是 | 五路开指令binary流经过base64加密 |

## 待处理页
### 输入
```
GET http://admin_fnsjs.gofishfarm.com/api/fault/5

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
        "info": 0,
        "fp_id": 5,
        "dtu_id": "517238110",
        "dtu_apikay": "21Gyq4=Sk0FloFckANE7MtFKFmw=",
        "lives": [
            "rtmp://dytl.game.caizs.com/live/5SXT00005?bizid=37147&txSecret=08cc216a98b7f8ab94fde68f6b7b5b69&txTime=5C763D49",
            "rtmp://dytl.game.caizs.com/live/3SXT00003?bizid=37147&txSecret=76b6a43e54dca9f9883fb1a438b6fded&txTime=5C763D49"
        ],
        "commands": {
            "on1": "AwUAAP8Ajdg=",
            "off1": "AwUAAAAAzCg=",
            "on2": "AwUAAf8A3Bg=",
            "off2": "AwUAAQAAneg=",
            "on3": "AwUAAv8ALBg=",
            "off3": "AwUAAgAAbeg=",
            "on4": "AwUAA/8Afdg=",
            "off4": "AwUAAwAAPCg=",
            "on5": "AwUABP8AzBk=",
            "off5": "AwUABAAAjek=",
            "on6": "AwUABf8Andk=",
            "off6": "AwUABQAA3Ck="
        },
        "on_time": 0,
        "off_time": 0,
        "fish_integration": 0
    }
}
```