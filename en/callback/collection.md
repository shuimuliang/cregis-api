# Callback > Collection

## Callback API

_The callback URL is provided in request body by the request initiator. For more details, see the `callback_url` parameter in the corresponding REQUEST API._

This API allows `cregis` to initiate callback request to the business. 

The callback comes in three scenarios, which are determined by the `status` in the callback content. These scenarios are mutually exclusive and only trigger once:

| status | Description      |
| ------ | ---------------- |
| 2      | Deposit Successful |
| 3      | Deposit Failed     |
| 4      | Timeout Canceled   |

If you need to re-push, you can log into the `cregis` client, select the corresponding project in the menu, and re-push it from the callback record.

> Note: Different types of businesses will have different callback content. It is strongly recommended to use different interfaces for different types of callbacks to ensure clear and specific business logic.

#### Request Method

HTTP POST

#### Request Parameters

| Name             | Type            | Required | Description         |
| ---------------- | --------------- | -------- | ------------------- |
| pid              | integer(int64)  | Yes      | Project ID          |
| chain_id         | string          | Yes      | Chain ID            |
| token_id         | string          | Yes      | Token ID            |
| currency         | string          | Yes      | Currency Identifier |
| address          | string          | Yes      | Address             |
| amount           | string          | Yes      | Amount              |
| real_amount      | string          | Yes      | Actual Amount       |
| third_party_id   | string          | Yes      | Caller Business ID  |
| status           | integer(int32)  | Yes      | Status              |
| txid             | string          | No       | Transaction Hash    |
| block_height     | string          | No       | Block Height        |
| block_time       | integer(int64)  | No       | Block Time          |
| nonce            | string          | Yes      | 6-digit random string |
| timestamp        | integer(int64)  | Yes      | Timestamp           |
| sign             | string          | Yes      | Signature           |

###### Example

```json
{
  "pid": 1382528827416576,
  "chain_id": "195",
  "token_id": "195",
  "currency": "TRX",
  "amount": "1.2",
  "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
  "real_amount": "1.2",
  "third_party_id": "c8fad34056714a539a5f33c3895ea133",
  "status": 1,
  "txid": "6dd05b0972075542219a3fcc116c58feaf9480f1f698cc46c4367ded83955cfd",
  "block_height": "34527604",
  "block_time": 1686814482000,
  "nonce": "ubqso3",
  "timestamp": 1687850657960,
  "sign": "f5be13fdd8c6f63951ca4427359457cb"
}
```