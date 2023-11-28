# 提币 > 发起

### 接入 API

POST /api/v1/payout

### 请求

#### 请求参数

| 名称               | 类型             | 必选 | 说明      |
| ---------------- | -------------- | -- | ------- |
| pid              | integer(int64) | 是  | 项目编号    |
| currency         | string         | 是  | 币种标识    |
| address          | string         | 是  | 地址      |
| amount           | string         | 是  | 金额      |
| callback\_url    | string         | 是  | 回调地址,该提币信息被处理时会向对应的callback_url发起回调通知,回调详情请参考[回调 > 提币](../callback/hui-tiao-ti-bi.md "mention")部分。    |
| third\_party\_id | string         | 是  | 调用方业务编号 |
| remark           | string         | 是  | 备注      |
| nonce            | string         | 是  | 6位随机字符串 |
| timestamp        | integer(int64) | 是  | 时间戳     |
| sign             | string         | 是  | 签名      |

###### 请求示例

```json
{
  "pid": 1382528827416576,
  "currency": "195@195",
  "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
  "amount": "1.1",
  "remark": "payout",
  "third_party_id": "c9231e604da54469a735af3f449c880f",
  "callback_url": "http://xxx.com/payout/callback",
  "nonce": "hwlkk6",
  "timestamp": 1688004243314,
  "sign": "d6eef2de79e39f434a38efb910213ba6"
}
```

### 返回

#### 返回结果

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回信息   |
| data | object | 返回数据对象 |

#### 返回数据`data`对象

| 名称  | 类型             | 说明    |
| --- | -------------- | ----- |
| cid | integer(int64) | 系统流水号 |

###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "cid": 1382688606330880
  }
}
```
