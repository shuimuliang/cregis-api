# 回调 > 地址充值

## 回调 API

_回调URL由对应业务发起方传入，具体了解对应REQUEST API中的`callback_url`参数_

该接口为`cregis`向业务发发起回调通知请求，该回调分两种情况，根据回调内容中的`status`判断，且两种情况是互斥的，只会产生一次回调：

| status |      说明      |
| ------ |    --------   |
| 1      | 充值交易成功回调 |
| 2      | 充值交易失败回调 |

发起回调后当接收到返回内容为`success`时为回调成功，否则为回调失败，回调失败可以进行重新推送，可登录`cregis`客户端，在项目菜单中选择对应项目，在回调记录菜单中重新推送。

> 不同类型的业务，回调内容不同，强烈建议使用不同的接口接收回调，保证业务逻辑的清晰明确。


#### 请求方式

HTTP POST

#### 请求参数

| 名称            | 类型             | 说明      |
| ------------- | -------------- | ------- |
| pid           | integer(int64) | 项目编号    |
| cid           | integer(int64) | 系统流水号    |
| chain\_id     | string         | 链编号     |
| token\_id     | string         | 代币编号    |
| currency      | string         | 币种标识    |
| address       | string         | 地址      |
| amount        | string         | 金额      |
| status        | integer(int32) | 状态      |
| txid          | string         | 交易hash  |
| block\_height | string         | 区块高度    |
| block\_time   | integer(int64) | 区块时间    |
| nonce         | string         | 6位随机字符串 |
| timestamp     | integer(int64) | 时间戳     |
| sign          | string         | 签名      |


###### 示例

```json
{
    "pid": 1382528827416576,
    "cid": 1391751691788288,
    "chain_id":"195",
    "token_id":"195",
    "currency": "TRX",
    "amount": "1.2",
    "address":"TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "status": 1,
    "txid": "6dd05b0972075542219a3fcc116c58feaf9480f1f698cc46c4367ded83955cfd",
    "block_height": "34527604",
    "block_time": 1686814482000,
    "nonce": "ubqso3",
    "timestamp": 1687850657960,
    "sign": "f5be13fdd8c6f63951ca4427359457cb"
}
```
