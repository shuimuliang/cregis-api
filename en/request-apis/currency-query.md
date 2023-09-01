# Currency > Query

### API URL

POST /api/v1/coins

Query the supported currency information of the project. The token-related information can be used in other APIs.

### Request

#### Request Parameters

| Name      | Type             | Required | Description             |
| --------- | -------------- | -------- | ----------------------- |
| pid       | integer(int64) | Yes      | Project ID              |
| nonce     | string         | Yes      | 6-digit random string   |
| timestamp | integer(int64) | Yes      | Timestamp               |
| sign      | string         | Yes      | Signature               |


###### Request Example

```
{
    "pid": 1382528827416576,
    "nonce": "m8jisx",
    "timestamp": 1687848653294,
    "sign": "cebd2bfd56766f1143dc40d078b64dac"
}
```

### Response

#### Response Parameters

| Name      | Type   | Description                |
| --------- | ------ | -------------------------- |
| code      | string | Response code              |
| msg       | string | Response message           |
| data      | object | Response data object       |

##### Response `data` object

| Name      | Type   | Description                       |
| --------- | ------ | --------------------------------- |
| coin_name | string | Token name                        |
| chain_id  | string | Chain ID                          |
| token_id  | string | Token ID, for tokens it's the contract address |

###### Response Example

```json
{
    "code": "00000",
    "msg": "ok",
    "data": {
        "payout_coins": [
            {
                "coin_name": "TRON#Shasta",
                "chain_id": "195",
                "token_id": "195"
            },
            {
                "coin_name": "Dogecoin",
                "chain_id": "3",
                "token_id": "3"
            }
        ],
        "order_coins": [
            {
                "coin_name": "TRON#Shasta",
                "chain_id": "195",
                "token_id": "195"
            },
            {
                "coin_name": "Dogecoin",
                "chain_id": "3",
                "token_id": "3"
            }
        ],
        "address_coins": [
            {
                "coin_name": "TRON#Shasta",
                "chain_id": "195",
                "token_id": "195"
            },
            {
                "coin_name": "Dogecoin",
                "chain_id": "3",
                "token_id": "3"
            }
        ]
    }
}
```
