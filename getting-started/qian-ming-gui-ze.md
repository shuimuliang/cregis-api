# 签名规则

## 签名算法

1） `body`参数中除去`sign`和空值参数外，其他参数**按字典序排序** :::highlight gray _字典序定义：在英文字典中，排列单词的顺序是先按照第一个字母以升序排列（即 a、b、c……z 的顺序）；如果第一个字母一样，那么比较第二个、第三个乃至后面的字母。如果比到最后两个单词不一样长（比如，sigh 和 sight），那么把短者排在前。_ ::: 2） 排序完成后，按照"`key1value1key2value2...`"进行拼接

3） 将项目的`API Key`拼接到第 2 步中得到的字符串最前面

4） 将第 3 步中获取的字符串使用散列算法取`md5`并转为小写即为`sign`，将`sign`添加到请求参数中

## 签名示例

假设项目`API Key`为：

```
f502a9ac9ca54327986f29c03b271491
```

**除 sign 外请求参数**为：

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

**第 2 步**（非空`keyvalue`按字典序排序）得到的字符串为：

```
addressTXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FSamount1.1callback_urlhttp://192.168.2.29:9099/callbackcurrency195@195noncemb8udupid1382528827416576remarkpayoutthird_party_id19faf9d3c8f34caf926f332f3021e887timestamp1688003966801
```

**第 3 步**（拼接项目`key`）的到字符串为：

```
f502a9ac9ca54327986f29c03b271491addressTXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FSamount1.1callback_urlhttp://192.168.2.29:9099/callbackcurrency195@195noncemb8udupid1382528827416576remarkpayoutthird_party_id19faf9d3c8f34caf926f332f3021e887timestamp1688003966801
```

**第 4 步**（取`md5`）得到的 sign 为：

```
c9bae061ae3f5f8d3bfde817f6966c36
```

**最终发送的请求参数**为（增加了`sign`）:

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
