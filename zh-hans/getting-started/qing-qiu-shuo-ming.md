# 请求说明

<mark style="color:orange;">项目接口，目前只支持</mark><mark style="color:orange;">`http`</mark> <mark style="color:orange;">`post`</mark> <mark style="color:orange;"></mark><mark style="color:orange;">一种请求方式，且指定的</mark><mark style="color:orange;">`body`</mark> <mark style="color:orange;">`Content-Type`</mark><mark style="color:orange;">为:</mark> <mark style="color:orange;"></mark><mark style="color:orange;">`application/json`</mark><mark style="color:orange;">。</mark><mark style="color:orange;">**请特别注意**</mark><mark style="color:orange;">，所有的请求参数通过</mark><mark style="color:orange;">`body`</mark><mark style="color:orange;">的</mark><mark style="color:orange;">`json`</mark><mark style="color:orange;">格式传递，其他传递参数的方式无效。</mark>

## 参数说明

项目接口，接口参数分为两部分：系统参数和业务参数。

### 系统参数

| 参数        | 类型     | 名称                                                        | 示例值                              | 是否必须 |
| --------- | ------ | --------------------------------------------------------- | -------------------------------- | ---- |
| timestamp | long   | 当前请求时间戳，单位毫秒                                              | 1687846491667                    | 是    |
| nonce     | string | 6 位随机字符串                                                  | 24abxo                           | 是    |
| sign      | string | 请求的数字签名，防止参数被非法篡改，签名规则参考以下 [签名规则](qian-ming-gui-ze.md) 章节 | eb881023045a167d3e4a7378bc212f53 | 是    |

### 业务参数

除了以上三个参数外，其他参数是业务参数，以下是一个请求示例。

## 请求示例

### 客户端

**以Postman为例：**&#x20;

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
