# 订单收款 > 取消

### 接入 API

POST /api/v1/deposit/cancel

### 请求

#### 请求参数

| 名称        | 类型             | 必选   | 说明      |
| --------- | -------------- | ---- | ------- |
| pid       | integer(int64) | true | 项目编号    |
| cid       | integer(int64) | true | 订单编号    |
| nonce     | string         | true | 6位随机字符串 |
| timestamp | integer(int64) | true | 时间戳     |
| sign      | string         | true | 签名      |

###### 请求示例

```json
{
    "pid": 1382528827416576,
    "cid": 1382625403125760,
    "nonce": "bw688v",
    "timestamp": 1687850871253,
    "sign": "93967ecbcbd0e696cac1aaf75f8b2bb9"
}
```

### 返回

#### 返回结果

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回信息   |
| data | object | 返回数据对象 |

###### 返回示例

```json
{
  "code": "00000",
  "msg": "success",
  "data": null
}
```
