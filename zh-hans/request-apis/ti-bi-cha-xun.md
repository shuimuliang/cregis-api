# 提币 > 查询

### 接入 API

POST /api/v1/payout/query

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
  "cid": 1382626461605888,
  "nonce": "sw7kv5",
  "timestamp": 1687853722065,
  "sign": "af825ddb839e6796d62977caf18d3394"
}
```

### 返回

#### 返回数据

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回信息   |
| data | object | 返回数据对象 |

#### 返回数据`data`对象

| 名称               | 类型             | 说明      |
| ---------------- | -------------- | ------- |
| pid              | integer(int64) | 项目编号    |
| chain\_id        | string         | 链编号     |
| token\_id        | string         | 代币编号    |
| currency         | string         | 币种标识    |
| address          | string         | 地址      |
| amount           | string         | 金额      |
| status           | integer(int32) | 状态      |
| third\_party\_id | string         | 调用方业务编号 |
| remark           | string         | 备注      |
| txid             | string         | 交易hash  |
| block\_height    | string         | 区块高度    |
| block\_time      | integer(int64) | 区块时间    |


###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "pid": 1382528827416576,
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "chain_id": "195",
    "token_id": "195",
    "currency": "TRX",
    "amount": "1.1",
    "third_party_id": "1e0fb3a0a9454ad8928d26b592e8b3c7",
    "remark": "payout",
    "status": 0,
    "txid": "6dd05b0972075542219a3fcc116c58feaf9480f1f698cc46c4367ded83955cfd",
    "block_height": "34527604",
    "block_time": 1686814482000
  }
}
```
