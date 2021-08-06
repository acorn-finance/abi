# Acorn ABIs

Chain: ThunderCore mainnet <108>

Website: https://acornstable.fi/

Documentation: https://docs.acornstable.fi/

### Address

| Contract | Address                                      | Proxy |                                  |
|:--------:|:--------------------------------------------:|:-----:|:---------------------------------|
|  Acorn   | `0x6E690DaC861fE7441770f84146F263d1CFBE909C` |       |                                  |
|  Oak     | `0xfc9733C2e5ee38b3dd2459DFa119FcdB33Bc7793` |   Y   |                                  |
|  AVault  | `0xccda6dC2B1DE0Ca7cCf702F40e52b8321b8be0e7` |       | Stake __3ACN__ for __Acorn__     |
|  AVault  | `0xb4097D3310642540970feb579a9Efd188EeeCc23` |       | Stake __Acorn LP__ for __Acorn__ |
|  NPool   | `0x51dAe6236FBd0C93D203C57193587261f76B58aA` |   Y   | 3ACN (BUSD/USDC/USDT Swap)       |


### Example

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
