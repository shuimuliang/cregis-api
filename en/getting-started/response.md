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

| Parameter   | Type     | Description                                                                                                        | Example        |
|-------------|----------|--------------------------------------------------------------------------------------------------------------------|----------------|
| code        | string   | Response status code. A `code` of `00000` indicates a successful response. For error codes, refer to [Return Codes](return-codes.md). | 00000          |
| msg         | string   | Error message corresponding to the `code`.          | "Signature Error"  |
| data        | object   | Contains the metadata in a JSON object format. This field remains empty if the request encounters an error.         | {}             |
