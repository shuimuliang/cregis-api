# Collection > Cancel

### API URL

POST /api/v1/deposit/cancel

### Request

#### Request Parameters

| Name      | Type             | Required | Description       |
| --------- | -------------- | -------- | ----------------- |
| pid       | integer(int64) | Yes      | Project Number    |
| cid       | integer(int64) | Yes      | Order Number      |
| nonce     | string         | Yes      | 6-digit random string |
| timestamp | integer(int64) | Yes      | Timestamp        |
| sign      | string         | Yes      | Signature        |

###### Request Example

```json
{
    "pid": 1382528827416576,
    "cid": 1382625403125760,
    "nonce": "bw688v",
    "timestamp": 1687850871253,
    "sign": "93967ecbcbd0e696cac1aaf75f8b2bb9"
}
```


### Response

#### Response Result

| Name | Type   | Description    |
| ---- | ------ | -------------- |
| code | string | Return Code    |
| msg  | string | Return Message |
| data | object | Return Data Object |

###### Response Example

```json
{
  "code": "00000",
  "msg": "success",
  "data": null
}
```

