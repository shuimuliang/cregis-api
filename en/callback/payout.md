# Callback > Payout

## Callback API

_The callback URL is provided in request body by the request initiator. For more details, see the `callback_url` parameter in the corresponding REQUEST API._

This API allows `cregis` to initiate callback request to the original API caller. 

The callback comes in four scenarios, which are determined by the `status` in the callback content. These scenarios are mutually exclusive and only trigger once:

| status | Description            |
| ------ | ---------------------- |
| 2      | Signature Rejected     |
| 4      | Approval Rejected      |
| 6      | Transaction Successful |
| 7      | Transaction Failed     |

After initiating the callback, when the returned content is `success`, the callback is successful. Otherwise, the callback fails. If the callback fails, you can push it again, you can log into the `cregis` client, select the corresponding project in the menu, and re-push it from the callback record.

> Note: Different types of callbacks will have different content. It is strongly recommended to use different APIs for different types of callbacks to ensure clear and specific business logic.


#### Request Method

HTTP POST

#### Request Parameters

| Name             | Type            | Description       |
| ---------------- | --------------- | ----------------- |
| pid              | integer(int64)  | Project ID        |
| cid              | integer(int64)  | Cregis ID        |
| chain_id         | string          | Chain ID          |
| token_id         | string          | Token ID          |
| currency         | string          | Currency Identifier |
| address          | string          | Address           |
| amount           | string          | Amount            |
| third_party_id   | string          | Caller's Customized ID |
| remark           | string          | Remarks           |
| status           | integer(int32)  | Status            |
| txid             | string          | Transaction Hash  |
| block_height     | string          | Block Height      |
| block_time       | integer(int64)  | Block Time        |
| nonce            | string          | 6-digit random string |
| timestamp        | integer(int64)  | Timestamp         |
| sign             | string          | Signature         |

###### Example

```json
{
  "pid": 1382528827416576,
  "cid": 1391751691788288,
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
  "block_time": 1686814482000,
  "nonce": "ubqso3",
  "timestamp": 1687850657960,
  "sign": "f5be13fdd8c6f63951ca4427359457cb"
}
```
