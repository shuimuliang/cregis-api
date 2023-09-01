# Response Guidelines

```json
{
  "code": "00000",
  "msg": "ok",
  "data": {
    "cid": 1382813146816512
  }
}
```

| Parameter   | Type     | Description                                                                        | Example   |
| ---- | ------ | ------------------------------------------------------------------------- | ----- |
| code | string | Response status code. A `code` of `00000` indicates a successful response, other codes indicate failure. Refer to [System Error Codes](fan-hui-ma.md) for specific system error codes.  | 00000 |
| msg  | string | Error message.                                                                          | Signature Error  |
| data | object | Business data, which is a Json object. If there's an error in the request, this field will be empty.                                              | {}    |
