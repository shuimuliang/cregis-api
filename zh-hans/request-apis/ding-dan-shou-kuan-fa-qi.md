# 订单收款 > 发起

### 接入 API

POST /api/v1/deposit

### 请求

#### 请求参数

| 名称               | 类型             | 必选    | 说明               |
| ---------------- | -------------- | ----- | ---------------- |
| pid              | integer(int64) | true  | 项目编号             |
| currency         | string         | true  | 币种标识             |
| amount           | string         | true  | 金额               |
| callback\_url    | string         | true  | 回调地址             |
| third\_party\_id | string         | true  | 调用方业务编号          |
| timeout          | integer(int32) | false | 超时时间（时间分钟），默认十分钟 |
| remark           | string         | false | 备注               |
| nonce            | string         | true  | 6位随机字符串          |
| timestamp        | integer(int64) | true  | 时间戳              |
| sign             | string         | true  | 签名               |

###### 请求示例

```json
{
  "pid": 1382528827416576,
  "callback_url": "http://xxxx.com/deposit/callback",
  "amount": "1.2",
  "currency": "TRON@Shasta",
  "remark": "423423",
  "third_party_id": "0828ebaa64f44b04a4da836b2c2d1da1",
  "timeout": 10,
  "nonce": "ubqso3",
  "timestamp": 1687850657960,
  "sign": "f5be13fdd8c6f63951ca4427359457cb"
}
```

### 返回

#### 返回结果

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回信息   |
| data | object | 返回数据对象 |

#### 返回数据`data`对象

| 名称      | 类型             | 说明    |
| ------- | -------------- | ----- |
| address | string         | 地址    |
| cid     | integer(int64) | 订单流水号 |


###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "cid": 1382686995161088,
    "address": "TBotPUNNgeSJmqWkSE7JoHdAnsdMyVnUca"
  }
}
```