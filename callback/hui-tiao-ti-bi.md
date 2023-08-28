# 回调 > 提币

## 回调 API

POST 回调URL由对应业务发起方传入，具体了解对应REQUEST API中的callback\_url参数

该接口为`cregis`向业务发发起回调通知请求，只要返回响应内容为`success`，即认为成功。如需要重新推送，可登录`cregis`客户端，在项目菜单中选择对应项目，在回调记录菜单中重新推送。

该回调分四种情况，根据回调内容中的`status`判断，且四种情况是互斥的，只会产生一次回调：

| status | 说明   |
| ------ | ---- |
| 2      | 签名驳回 |
| 4      | 审批驳回 |
| 6      | 交易成功 |
| 7      | 交易失败 |

不同类型的业务，回调内容不同，强烈建议使用不同的接口接收回调，保证业务逻辑的清晰明确，不要使用同一个接口接收不同类型业务的回调。

> Body 请求参数

```json
{
  "pid": 1382528827416576,
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

#### 请求参数

| 名称               | 类型             | 说明      |
| ---------------- | -------------- | ------- |
| pid              | integer(int64) | 项目编号    |
| chain\_id        | string         | 链编号     |
| token\_id        | string         | 代币编号    |
| currency         | string         | 币种标识    |
| address          | string         | 地址      |
| amount           | string         | 金额      |
| third\_party\_id | string         | 调用方业务编号 |
| remark           | string         | 备注      |
| status           | integer(int32) | 状态      |
| txid             | string         | 交易hash  |
| block\_height    | string         | 区块高度    |
| block\_time      | integer(int64) | 区块时间    |
| nonce            | string         | 6位随机字符串 |
| timestamp        | integer(int64) | 时间戳     |
| sign             | string         | 签名      |

**status枚举值**

| 属性 | 值    |
| -- | ---- |
| 2  | 签名驳回 |
| 4  | 审批驳回 |
| 6  | 交易成功 |
| 7  | 交易失败 |
