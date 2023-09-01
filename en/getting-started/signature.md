# Signature

## Signature Algorithm

1) From the request parameters, exclude `sign` and all parameters with null or empty values. Then, **sort the remaining parameters lexicographically**. 

_Lexicographical Definition: In English dictionaries, words are arranged in order of the first letter (i.e., in the sequence a, b, c... z). If the first letter is the same, compare the second, third, and subsequent letters. If by the end the two words are of different lengths (e.g., "sigh" and "sight"), place the shorter one first._

2) After sorting, concatenate the parameters in the format "`key1value1key2value2...`".

3) Prepend the `API Key` to the string obtained from step 2.

4) Convert the string from step 3 into an `md5` hash, in lowercase, to get the `sign`. Include this `sign` in the request parameters.

## Signature Example

**step 1** Assuming the `API Key` is:

```
f502a9ac9ca54327986f29c03b271491
```

The **request parameters excluding sign** are:


```json
{
  "pid": 1382528827416576,
  "currency": "195@195",
  "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
  "amount": "1.1",
  "remark": "payout",
  "third_party_id": "c9231e604da54469a735af3f449c880f",
  "callback_url": "http://192.168.2.29:9099/callback",
  "nonce": "hwlkk6",
  "timestamp": 1688004243314
}
```

**step 2**（非空`keyvalue`按字典序排序）得到的字符串为：

```
addressTXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FSamount1.1callback_urlhttp://192.168.2.29:9099/callbackcurrency195@195noncemb8udupid1382528827416576remarkpayoutthird_party_id19faf9d3c8f34caf926f332f3021e887timestamp1688003966801
```

**step 3**（拼接项目`key`）的到字符串为：

```
f502a9ac9ca54327986f29c03b271491addressTXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FSamount1.1callback_urlhttp://192.168.2.29:9099/callbackcurrency195@195noncemb8udupid1382528827416576remarkpayoutthird_party_id19faf9d3c8f34caf926f332f3021e887timestamp1688003966801
```

**step 4**（取`md5`）得到的 sign 为：

```
c9bae061ae3f5f8d3bfde817f6966c36
```

**final step**（增加了`sign`）:

```json
{
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
}
```
