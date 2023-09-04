# Payout > Query

### API URL

POST /api/v1/payout/query

### Request

#### Request Parameters
| Name       | Type           | Required | Description          |
|------------|----------------|----------|----------------------|
| pid        | integer(int64) | true     | Project ID           |
| cid        | integer(int64) | true     | Order Serial Number  |
| nonce      | string         | true     | 6-character random string |
| timestamp  | integer(int64) | true     | Timestamp            |
| sign       | string         | true     | Signature            |


###### Request Example

```json
{
  "pid": 1382528827416576,
  "cid": 1382626461605888,
  "nonce": "sw7kv5",
  "timestamp": 1687853722065,
  "sign": "af825ddb839e6796d62977caf18d3394"
}
```

### Response

#### Response Result

| Name  | Type     | Description          |
| ----- | ------ | --------------------- |
| code  | string | Response Code           |
| msg   | string | Response Message        |
| data  | object | Response Data Object    |

#### Response `data` Object

| Name           | Type           | Description            |
|----------------|----------------|------------------------|
| pid            | integer(int64) | Project ID             |
| chain_id       | string         | Chain ID               |
| token_id       | string         | Token ID               |
| currency       | string         | Currency Identifier    |
| address        | string         | Address                |
| amount         | string         | Amount                 |
| status         | integer(int32) | Status                 |
| third_party_id | string         | Caller Customized ID   |
| remark         | string         | Remark                 |
| txid           | string         | Transaction Hash       |
| block_height   | string         | Block Height           |
| block_time     | integer(int64) | Block Time             |


###### Response Example

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