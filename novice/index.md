# 新手指南步骤时长
```
接口地址： http://www.gofishfarm.com/novices
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
|　└─list | array | 否 | 步骤时长记录表 |
|　 　　├─step1 | int | 是 | 第一步视频时长**单位皆为毫秒** |
|　 　　├─step2 | int | 是 | 第二步视频时长 |
|　 　　├─step3 | int | 是 | 第三步视频时长 |
|　 　　├─step4 | int | 是 | 第四步视频时长 |
|　 　　├─step5 | int | 是 | 第五步视频时长 |
|　 　　├─step6 | int | 是 | 第六步视频时长 |
|　 　　├─step7 | int | 是 | 第七步视频时长 |
|　 　　├─step8 | int | 是 | 第八步视频时长 |
|　 　　├─step9 | int | 是 | 第九步视频时长 |
|　 　　├─step10 | int | 是 | 第十步视频时长 |
|　 　　└─step11 | int | 是 | 第十一步视频时长 |


## 范例

### 输入
```
GET http://www.gofishfarm.com/novices

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
        "list": {
            "step1": 1000,
            "step2": 1000,
            "step3": 1000,
            "step4": 1000,
            "step5": 1000,
            "step6": 1000,
            "step7": 1000,
            "step8": 1000,
            "step9": 1000,
            "step10": 1000,
            "step11": 1000
        }
    }
}
```