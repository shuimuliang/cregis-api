# 订单收款 > 查询

## 接入 API

POST /api/v1/deposit/query

> Body 请求参数

```json
{
  "pid": 1382528827416576,
  "cid": 1382625403125760,
  "nonce": "pfvt1t",
  "timestamp": 1687851045181,
  "sign": "93aad14ccb8109cfafd68f024fe7248a"
}
```

#### 请求参数

| 名称        | 类型             | 必选 | 说明      |
| --------- | -------------- | -- | ------- |
| pid       | integer(int64) | 是  | 项目编号    |
| cid       | integer(int64) | 是  | 订单编号    |
| nonce     | string         | 是  | 6位随机字符串 |
| timestamp | integer(int64) | 是  | 时间戳     |
| sign      | string         | 是  | 签名      |

> 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "pid": 1382528827416576,
    "address": "",
    "chain_id": "195",
    "token_id": "195",
    "currency": "TRX",
    "amount": "1.2",
    "real_amount": "0",
    "third_party_id": "c8fad34056714a539a5f33c3895ea133",
    "status": 1,
    "txid": "6dd05b0972075542219a3fcc116c58feaf9480f1f698cc46c4367ded83955cfd",
    "block_height": "34527604",
    "block_time": 1686814482000
  }
}
```

#### 返回结果

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回信息   |
| data | object | 返回数据对象 |

#### 返回数据对象

| 名称               | 类型             | 说明      |
| ---------------- | -------------- | ------- |
| pid              | integer(int64) | 项目编号    |
| address          | string         | 地址      |
| chain\_id        | string         | 链编号     |
| token\_id        | string         | 代币编号    |
| currency         | string         | 币种标识    |
| amount           | string         | 金额      |
| real\_amount     | string         | 实际金额    |
| status           | integer(int32) | 状态      |
| third\_party\_id | string         | 调用方业务编号 |
| txid             | string         | 交易hash  |
| block\_height    | string         | 交易高度    |
| block\_time      | integer(int64) | 交易时间戳   |

**status枚举值**

| 值 | 说明   |
| - | ---- |
| 0 | 待确认  |
| 1 | 成功   |
| 2 | 失败   |
| 3 | 超时取消 |
| 4 | 人工取消 |
