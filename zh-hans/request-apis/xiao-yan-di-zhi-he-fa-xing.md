# 校验 > 地址合法性

### 接入 API

POST /api/v1/address/legal

检验地址格式合法性，可在发起提币前进行校验，检测到账地址合法再执行提币操作

### 请求

#### 请求参数

| 名称        | 类型             | 必选 | 说明      |
| --------- | -------------- | -- | ------- |
| pid       | integer(int64) | 是  | 项目编号    |
| address   | string         | 是  | 地址      |
| chain\_id | string         | 是  | 链编号     |
| nonce     | string         | 是  | 6位随机字符串 |
| timestamp | integer(int64) | 是  | 时间戳     |
| sign      | string         | 是  | 签名      |

###### 请求示例

```json
{
    "pid": 1382528827416576,
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "chain_id": "195",
    "nonce": "m8jisx",
    "timestamp": 1687848653294,
    "sign": "cebd2bfd56766f1143dc40d078b64dac"
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

| 名称     | 类型      | 说明                             |
| ------ | ------- | ------------------------------ |
| result | boolean | <p>true：合法地址<br>false：非法地址</p> |

###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "result": true
  }
}
```
