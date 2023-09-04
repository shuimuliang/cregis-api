# Address Deposit > Create Address

### API URL

POST /api/v1/address/create

### Request

#### Request Parameters

| Parameter     | Type            | Required | Description   |
| ------------- | --------------- | -------- | ------------- |
| pid           | integer(int64)  | Yes      | Project ID    |
| chain_id      | string          | Yes      | Chain ID      |
| alias         | string          | Yes      | Display Name  |
| callback_url  | string          | Yes      | Callback URL, If funds are received through an address generated by this API, refer to [Callback > Address Deposit](callback/address-deposit.md) section for callback details.  |
| nonce         | string          | Yes      | 6-character random string |
| timestamp     | integer(int64)  | Yes      | Timestamp     |
| sign          | string          | Yes      | Signature     |

###### Request Example

```json
{
  "pid": 1382528827416576,
  "callback_url": "http://xxxx.com/deposit/callback",
  "chain_id": "60",
  "alias": "cc",
  "nonce": "ubqso3",
  "timestamp": 1687850657960,
  "sign": "f5be13fdd8c6f63951ca4427359457cb"
}
```
### Response

#### Response Result

| Name  | Type   | Description      |
| ----- | ------ | ---------------- |
| code  | string | Response code    |
| msg   | string | Response message |
| data  | object | Response data object |

#### Response `data` Object

| Name    | Type   | Description |
| ------- | ------ | ----------- |
| address | string | Address     |

###### Response Example

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "address": "TBotPUNNgeSJmqWkSE7JoHdAnsdMyVnUca"
  }
}
```
