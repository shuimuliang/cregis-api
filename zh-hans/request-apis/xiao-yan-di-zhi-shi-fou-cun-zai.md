# 校验 > 地址是否存在

### 接入 API

POST /api/v1/address/inner

校验地址是否为对应项目的地址，可在订单发起后，对返回的地址信息进行校验，防止地址被篡改

### 请求

#### 请求参数

| 名称        | 类型             | 必选   | 说明      |
| --------- | -------------- | ---- | ------- |
| pid       | integer(int64) | true | 项目编号    |
| address   | string         | true | 地址      |
| chain\_id | string         | true | 链编号     |
| nonce     | string         | true | 6位随机字符串 |
| timestamp | integer(int64) | true | 时间戳     |
| sign      | string         | true | 签名      |


###### 请求示例
```json
{
    "pid": 1382528827416576,
    "address": "TXsmKpEuW7qWnXzJLGP9eDLvWPR2GRn1FS",
    "chain_id": "195",
    "nonce": "tvccuh",
    "timestamp": 1687849472174,
    "sign": "48036043999446485fe0d20a838a00dc"
}
```

### 返回

#### 返回结果

| 名称   | 类型     | 说明     |
| ---- | ------ | ------ |
| code | string | 返回码    |
| msg  | string | 返回说明   |
| data | object | 返回数据对象 |

#### 返回数据`data`对象

| 名称     | 类型      | 说明                                       |
| ------ | ------- | ---------------------------------------- |
| result | boolean | <p>true：地址是项目内地址<br>false：地址不是项目内部地址</p> |


###### 返回示例

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "result": false
  }
}
```
