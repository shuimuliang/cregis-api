# Request Guidelines

The `cregis` API only supports the `POST` method over `http`. Ensure that the `Content-Type` is set to `application/json`. **Please pay special attention** that all request parameters are accepted in `JSON` format. Any other methods for passing parameters will be invalid.

## Parameters

API request parameters are categorized into two parts: 
- **System Parameters**: Parameters that are necessary for every API call.
- **Specific Parameters**: Parameters specific to individual API calls or endpoints.



### System Parameters

| Parameter        | Type     | Description                                                        | Example                              | Required |
| --------- | ------ | --------------------------------------------------------- | -------------------------------- | ---- |
| timestamp | long   | Current request timestamp in milliseconds                                              | 1687846491667                    | yes    |
| nonce     | string | A 6-character random string                                                  | 24abxo                           | yes    |
| sign      | string | The digital signature of the request to prevent illegal tampering. Refer to the [Signature](signature.md) section for the signing rules. | eb881023045a167d3e4a7378bc212f53 | yes    |

### Functional Parameters

Apart from the three parameters above, other parameters are Functional Parameters. Below is a request example.

## Request Example

### Client

**Using Postman as an example:**&#x20;

![image-20230629100648945.png](https://api.apifox.cn/api/v1/projects/2923699/resources/393696/image-preview)

### curl

```
curl --location --request POST 'https://xx.xx.xx/api/v1/payout' \
--header 'Content-Type: application/json' \
--data-raw '{
    "pid": 1382528827416576,
    "currency": "195@195",
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "amount": "1.1",
    "remark": "payout",
    "third_party_id": "c9231e604da54469a735af3f449c880f",
    "callback_url": "http://192.168.2.29:9099/callback",
    "nonce": "hwlkk6",
    "timestamp": 1688004243314,
    "sign": "d6eef2de79e39f434a38efb910213ba6"
}'
```
