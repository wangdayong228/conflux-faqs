
### 如何发送交易?
发送交易最简单的方式是使用钱包比如：Conflux Portal，DappBirds 等，点击发送直接设置金额即可。
如果你是一个开发者，你可以使用 Conflux SDK（JS，Java，Go） 自行构建交易，然后通过 node RPC 发送到链上。


### 发送交易时的 `燃气费`，`存储费` 指的是什么？
燃气费是交易执行的手续费, 矿工打包并执行交易需要收取一定的费用，其计算方式为 gasFee = gasPrice * gasUsed。
交易的执行可能会占用新的存储空间，此部分空间的占用不需要支付费用，但需要为存储的使用抵押一部分 CFX，随着存储的释放，抵押也会归还。
存储费指的的存储占用抵押的 CFX，每占用 1024 字节需要抵押 1 CFX。


### 使用 SDK 发送交易，需要指定什么信息（参数）
使用 JS-SDK 发送交易，如果只进行简单的 CFX 转账，只需指定 `from`(从哪个账户转出), `to`（发到哪个账户）, `value`（发送数量，单位是Drip）即可。


### 除了 from, to, value 一笔 TX 还包含哪些信息?

* `from`: 交易的发出方地址，不能为空，且只能是普通账户地址，不能是合约
* `to`: 交易的接手方，可以为空, 如果为空，则会使用 data 信息创建智能合约，新创建合约的地址可以在 receipt 中获取
* `value`: 交易的金额，单位为 Drip
* `nonce`: 交易执行的序号，通常该续号从0开始，每发送一笔交易加 1，交易的执行也会按照递增的顺序执行，不会跳跃，cfx_getNextNonce 可以获取某地址的 nonce
* `gas`: 交易执行所能消耗的燃气费数量上限，
* `gasPrice`: 交易燃气费的价格，单位为 Drip
* `storageLimit`: 交易执行所能支付的存储最大上限
* `chainId`: 链的ID
* `epochNumber`:
* `data`: 交易的数据，可以是备注，也可以是合约创建 ByteCode，或者是合约交互的 data


### 如何获取正确的 nonce?

### nonce 什么时候回加 1？ 交易执行失败 nonce 会加 1 么？为什么交易发送了，nonce 没有变化？


### 交易实际使用的燃气费如何计算 ？

### 如何释放存储占用 ？

### 为什么跟合约交互，交易消耗了燃气费，但我的余额没有变？

### 如果要批量发送交易，如何管理 nonce ？

### 如何知道一笔交易所能使用的 gas 和 storage ?


### 怎么知道一笔交易执行成功了 ？

### 怎么判断一笔交易是否安全，是否被确认?

### `receipt` 是什么, 都包含什么信息 ?

### 为什么交易发送失败 ？

### 为什么交易一直不被打包 ？

### 为什么交易执行失败 ？
