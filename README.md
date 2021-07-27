# Acorn ABIs

Web3.js Example:

```js
const abi = require('./NPool.abi.json')

// 3 Acorn Pool (BUSD / USDC / USDT)
const pool = new web3.eth.Contract(abi, '0x51dAe6236FBd0C93D203C57193587261f76B58aA')

pool.methods.get_dy(0, 1, 10n**18n).call() // Query: how much USDC(1) will get if we spend 1 BUSD(0)
// '1002745'   (1.0027 USDC)

pool.methods.get_dx(1, 2, 1e6).call() // Query: how much USDC(1) is required if we want 1 USDT(2)
// '1001357'   (1.001357 USDC)
```
