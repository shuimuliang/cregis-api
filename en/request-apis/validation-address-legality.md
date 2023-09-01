# Verification > Address Legality

### API URL

POST /api/v1/address/legal

Verify the legality of the address format. It can be verified before initiating a withdrawal to ensure the receiving address is valid before executing the withdrawal operation.

### Request

#### Request Parameters

| Name      | Type             | Required | Description             |
| --------- | -------------- | -------- | ----------------------- |
| pid       | integer(int64) | Yes      | Project ID              |
| address   | string         | Yes      | Address                 |
| chain_id  | string         | Yes      | Chain ID                |
| nonce     | string         | Yes      | 6-digit random string   |
| timestamp | integer(int64) | Yes      | Timestamp               |
| sign      | string         | Yes      | Signature               |

###### Request Example

```json
{
    "pid": 1382528827416576,
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "chain_id": "195",
    "nonce": "m8jisx",
    "timestamp": 1687848653294,
    "sign": "cebd2bfd56766f1143dc40d078b64dac"
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

| Name   | Type    | Description                       |
| ------ | ------- | --------------------------------- |
| result | boolean | true: Valid address, false: Invalid address |


###### Response Example

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "result": true
  }
}
```
