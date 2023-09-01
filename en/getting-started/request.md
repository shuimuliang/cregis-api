# Request Guidelines

<mark style="color:orange;">The project interface currently only supports the </mark><mark style="color:orange;">`http`</mark> <mark style="color:orange;">`POST`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">method and the specified</mark> <mark style="color:orange;">`Content-Type`</mark><mark style="color:orange;"> is:</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`application/json`</mark><mark style="color:orange;">.</mark><mark style="color:orange;"> **Please pay special attention**</mark><mark style="color:orange;">, that all request parameters are passed through the `json`</mark><mark style="color:orange;"> format, any other methods of passing parameters will be invalid.</mark>

## Parameters

For the project interface, the parameters are divided into two parts: system parameters and business parameters.


### System Parameters

| Parameter        | Type     | Description                                                        | Example                              | Required |
| --------- | ------ | --------------------------------------------------------- | -------------------------------- | ---- |
| timestamp | long   | Current request timestamp in milliseconds                                              | 1687846491667                    | 是    |
| nonce     | string | A 6-character random string                                                  | 24abxo                           | 是    |
| sign      | string | The digital signature of the request to prevent illegal tampering. Refer to the [Signature Rules](signature-rules.md) section for the signing rules. | eb881023045a167d3e4a7378bc212f53 | 是    |

### Business Parameters

Apart from the three parameters above, other parameters are business parameters. Below is a request example.

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
