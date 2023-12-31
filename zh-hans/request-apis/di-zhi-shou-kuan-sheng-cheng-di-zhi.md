# 地址收款 > 生成地址

### 接入 API

POST /api/v1/address/create

### 请求

#### 请求参数

| 名称            | 类型             | 必选   | 说明      |
| ------------- | -------------- | ---- | ------- |
| pid           | integer(int64) | true | 项目编号    |
| chain\_id     | string         | true | 链id     |
| alias         | string         | false | 地址显示名称  |
| callback\_url | string         | true | 回调地址,该地址接收资金时会向对应的callback_url发起交易回调通知,回调详情请参考[回调 > 地址充值](../callback/hui-tiao-di-zhi-chong-zhi.md "mention")部分。    |
| nonce         | string         | true | 6位随机字符串 |
| timestamp     | integer(int64) | true | 时间戳     |
| sign          | string         | true | 签名      |

###### 请求示例

```json
{
  "pid": 1382528827416576,
  "callback_url": "http://xxxx.com/deposit/callback",
  "chain_id": "60",
  "alias": "cc",
  "nonce": "ubqso3",
  "timestamp": 1687850657960,
  "sign": "f5be13fdd8c6f63951ca4427359457cb"
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

| 名称      | 类型     | 说明 |
| ------- | ------ | -- |
| address | string | 地址 |

###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "address": "TBotPUNNgeSJmqWkSE7JoHdAnsdMyVnUca"
  }
}
```

