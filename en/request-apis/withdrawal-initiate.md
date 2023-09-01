# Withdrawal > Initiate

### API URL

POST /api/v1/payout

### Request

#### Request Parameters

| Name           | Type             | Required | Description        |
| -------------- | -------------- | -------- | ------------------ |
| pid            | integer(int64) | Yes      | Project Number     |
| currency       | string         | Yes      | Currency Identifier|
| address        | string         | Yes      | Address            |
| amount         | string         | Yes      | Amount             |
| callback_url   | string         | Yes      | Callback Address   |
| third_party_id | string         | Yes      | Caller Business Number |
| remark         | string         | Yes      | Remark             |
| nonce          | string         | Yes      | 6-digit random string  |
| timestamp      | integer(int64) | Yes      | Timestamp          |
| sign           | string         | Yes      | Signature          |

###### Request Example

```json
{
  "pid": 1382528827416576,
  "currency": "195@195",
  "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
  "amount": "1.1",
  "remark": "payout",
  "third_party_id": "c9231e604da54469a735af3f449c880f",
  "callback_url": "http://xxx.com/payout/callback",
  "nonce": "hwlkk6",
  "timestamp": 1688004243314,
  "sign": "d6eef2de79e39f434a38efb910213ba6"
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

| Name | Type             | Description      |
| ---- | -------------- | ---------------- |
| cid  | integer(int64) | System Sequence Number |


###### Response Example

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "cid": 1382688606330880
  }
}
```

