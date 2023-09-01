# 币种码

## 格式

`currency`支持两种格式：

* 币种名称（`name`）
* 链编号@币种编号（`chain_id@token_id`）

## 举例

以下表格中前两个币种的`currency`参数分别为：

* `Ethereum` 或 `60@60`
* `USDT-ERC20` 或 `60@0xdac17f958d2ee523a2206206994597c13d831ec7`

## 编码列表

| name            | chain\_id | token\_id                                  |
| --------------- | --------- | ------------------------------------------ |
| Ethereum        | 60        | 60                                         |
| USDT-ERC20      | 60        | 0xdac17f958d2ee523a2206206994597c13d831ec7 |
| USDC-ERC20      | 60        | 0xa0b86991c6218b36c1d19d4a2e9eb0ce3606eb48 |
| MATIC-ERC20     | 60        | 0x7d1afa7b718fb893db30a3abc0cfc608aacfebb0 |
| Uniswap-ERC20   | 60        | 0x1f9840a85d5af5bf1d1762f925bdaddc4201f984 |
| ChainLink-ERC20 | 60        | 0x514910771af9ca656af840dff83e8264ecf986ca |
| SHIBA-ERC20     | 60        | 0x95ad61b0a150d79219dcf64e1e6cc01f0b64c4ce |
| TRON            | 195       | 195                                        |
| USDT-TRC20      | 195       | TR7NHqjeKQxGTCi8q8ZY4pL8otSzgjLj6t         |
| USDC-TRC20      | 195       | TEkxiTehnzSmSe2XqrBj4w32RUN966rdz8         |
| BNB-BSC         | 2510      | 2510                                       |
| USDT-BEP20      | 2510      | 0x55d398326f99059ff775485246999027b3197955 |
| USDC-BEP20      | 2510      | 0x8ac76a51cc950d9822d68b83fe1ad97b32cd580d |
