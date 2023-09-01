# Verification > Address Existence

### API URL

POST /api/v1/address/inner

Check if the address belongs to the corresponding project. After initiating the order, you can validate the returned address information to prevent the address from being tampered with.

### Request

#### Request Parameters

| Name      | Type           | Required | Description     |
| --------- | -------------- | -------- | --------------- |
| pid       | integer(int64) | true     | Project ID      |
| address   | string         | true     | Address         |
| chain_id  | string         | true     | Chain ID        |
| nonce     | string         | true     | 6-character random string |
| timestamp | integer(int64) | true     | Timestamp       |
| sign      | string         | true     | Signature       |

###### Request Example

```json
{
    "pid": 1382528827416576,
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "chain_id": "195",
    "nonce": "tvccuh",
    "timestamp": 1687849472174,
    "sign": "48036043999446485fe0d20a838a00dc"
}
```

### Response

#### Response Result

| Name  | Type   | Description        |
| ----- | ------ | ------------------ |
| code  | string | Response code      |
| msg   | string | Response message   |
| data  | object | Response data object |

#### Response `data` Object

| Name   | Type    | Description                                            |
| ------ | ------- | ------------------------------------------------------ |
| result | boolean | <p>true: Address is within the project<br>false: Address is not within the project</p> |


###### Response Example

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "result": false
  }
}
```


