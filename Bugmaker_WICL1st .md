# Web3 URL 残酷共学第 1 期残酷指引

> ⚠️ 正式开始前请确保你在身体上和精神上都处于合适的状态，请刻意练习，残酷面对 🆒。为方便检索 The First Web3 URL Intensive CoLearning 简写为 WICL1st，第 2 期即为WICL2nd，第 3 期即为 WICL3rd，以此类推。

> ⚠️ 报名需要按要求认真填写下面 [ XXX ] 部分，方可通过报名审核，通过审核即可开始自主学习。

---

# [ 你的名字 ]

1. **自我介绍：**

   Bugmaker [ from Cuit，web3 learner，focus on smart contract build and Solidity related project develop ,graduate in 2 years ]

2. **组队期待：**

   长期 [ 寻找区区块链开发的黑客松队友 ]

3. **你认为你会完成本次 Web3 URL 的残酷学习吗？**

   Yes [ Yes 100% or Maybe xx% ]

---

## 第 1 期共学时间计划

- **7 月 8 日 - 7 月 14 日**：

  - 自我介绍：大家按要求更新上方自我介绍，方面大家互相了解，及后续自由组队方向。

  -  [Web3 URL 残酷共学频道](https://t.me/LXDAO/8748)报道：大家可以自由在残酷共学群里交流分享，互动答疑，根据自身学习阶段情况随时开启自由组队。

  - 课前学习：了解残酷共学流程，GitHub 协作共学基础；Web3:// 协议课前学习。

- **7 月 15 日 - 7 月 21 日**：

  - **7 月 15 日 周一晚 8 点- 9 点（北京时间）：** 第 1 次公开课分享
  - **本周共学内容：** 涉及 Web3://  的背景和演进历史；支持 Web3://  协议的访问方式 (gateway 和 EVM browser)来浏览以太坊上面的数据；熟悉使用 Web3://  和 EthStorage 早期测试网来部署简单的去中心化网站。
  - **Homework1：** 见[课程 PPT](https://docs.google.com/presentation/d/1egJUKJrjC9wjkmOF9sLBkTSwHpd6hl8FXkWehPW7kFk/edit#slide=id.g1754f50a55c_0_11)。

- **7 月 22 日 - 7 月 28 日**
  - **7 月 22 日 周一晚 8 点- 9 点（北京时间）：** 第 2 次公开课分享

  - **本周共学内容：** 涉及 Web3://  高级开发工具，包括：在命令行通过 web3curl 来通过 Web3://  协议下载数据，通过 ethfs-uploader 批量上传网页数据，通过 manual 模式来搭建去中心化多人交互全链网站；及深入理解以太坊的存储模型和 gas 开销等。
  - **边学边用实战开发：** 根据组队情况自由安排。
  - **Homework2：** 见[课程 PPT](https://docs.google.com/presentation/d/1egJUKJrjC9wjkmOF9sLBkTSwHpd6hl8FXkWehPW7kFk/edit#slide=id.g1754f50a55c_0_11)。

- **7 月 29 日 - 8 月 4 日**
  - **7 月 29 日 周一晚 8 点- 9 点（北京时间）：** 第 3 次公开课分享
  - **本周共学内容：** 涉及实际应用案例分享及未来以太坊基础设施在 Web3://  的重要作用及开发方向等。
  - **边学边用实战开发：** 根据组队情况自由安排。
  - **结营分享：** 具体时间及详情另在「Web3 URL 残酷共学频道」通知。

---

## 笔记证明 Notes Proof
<!-- Content_START --> 
### 07.13
- 今日学习时间：7.13 9 a.m--12 a.m
- 学习内容小结：`solidity`语法回顾  
`require`语句的用法  
`msg.sender&&t.orign`的区别（`msg.sender`指的是函数的调用者，`tx.orign`指的是合约总的发起人，一般是钱包地址）  
`mapping`的用法，包括赋值、查询、删除语句  
`引用类型`：对于已分配好的引用类型，对原有值的改变*不会*影响现有值  
`字符串`：string.concat--字符串连接，bytes().length--获取字符串长度  
复习了常见的控制流语句
### 07.14
- 今日学习时间：7.14 2 p.m--5 p.m
- 学习内容小结：`Uniswap V2`概念学习  

*Flash Swap*   
>Uniswap v2增加了一个新特性，允许用户在支付费用前先收到并使用代币，只要他们在同一个交易中完成支付。swap方法会在转出代币和检查k值两个步骤之间，调用一个可选的用户指定的回调合约。一旦回调完成，Uniswap合约会检查当前代币余额，并且确认其满足k值条件（在扣除手续费后）。如果当前合约没有足够的余额，整个交易将被回滚。
利用的是以太坊交易的原子性，用户已经接受到代币，后续如果检查k值不符合规定，就会回滚交易，整个交易不会被确认，即用户不会收到闪电贷的代币。  

*WAP--时间加权*
>由于uniswap的价格定义规则，币价由上个区块最后记录的价格决定。在新一笔交易确认之前，修改上个区块的币价，则会导致币价波动。
假设交易池中有a 200、b 100，以a的来表示b的价格则为b=2a
若在下一笔交易产生之前，向交易池中发送100b，这是b的价格则为b=a，而不是b=2a
这样币价在短时间内偏离了市场价格，可能导致攻击者进行套利操作  
此时Uniswap就采用了TWAP进行控制币价短时间波动  

*手续费*  
>Uniswap 手续费为交易额的0.3%，手续费会根据权重分给LP，交易保证池子满足x*y=k，代币数量可能会发生改变，但是x与y的乘积不变。  
手续费会增加交易池的价值，币的总数可能也会改变。  

*流动性代币*
>流动性代币（Liquidity Tokens），有时称为流动性提供者代币（LP Tokens），是由去中心化交易所（如Uniswap）发行的代币，用来表示流动性提供者在特定流动性池中的份额。当流动性提供者向流动性池中注入代币时，他们会收到相应的流动性代币作为凭证。
>流动性代币的数量与交易池中的总价值成比例。例如，如果用户提供了流动性池10%的代币，他们将获得总流动性代币的10%。
*首次铸币攻击*
>首次铸币攻击是指攻击者在第一次添加流动性时存入最小单位（10的-18次方，即1 wei）的流动性，比如1 wei ABC和1 wei XYZ，此时将铸造1 wei 流动性代币（根号1，二者乘积的算数平方根）；同时，攻击者在同一个交易中继续向池子转入（非铸造）100万个ABC和100万个XYZ，接着调用 sync()方法更新缓存余额，此时1 wei的流动性代币价值100万+(10的-18次方)ABC和100万+(10的-18次方)XYZ。因为这是交易的最小单位，其他流动性参与者要想添加流动性，需要等价的大量代币，其价格可能高到大部分人无法参与。
### 07.15
- 今日学习时间：7.15  9 a.m.--2 p.m.
- 学习内容小结：Solidity 语法复习  
##### `try-catch` 语法  
##### `library`库函数用法
>库函数属性无论为`internal`还是`public`，都可以被合约所调用。调用`internal`属性的函数，等同于调用合约内部的`internal`属性的函数，无需额外的`gas`消耗；而调用`public`属性的函数则等同于合约`public`函数的调用，会产生额外的合约调用开销。  
使用`using for`，可将库函数作为成员变量赋值给类型，例如，`using Math for uint256` 表示之后，`uint256`类型的数据可以直接调用`Math`库中的函数，并将自身作为第一个参数。    

##### Override&&Virtual  
>只有被`Virtual`定义的函数，才能被重写。重写的函数必须保证参数列表和返回值类型一致。这包括参数的顺序、类型和名称。  
重写需要有`override`属性  
#### FAQ
>枚举能和整型进行类型转换吗？  
  枚举类型可以与整数进行显式转换，但不能进行隐式转换。  

```solidity
//修饰符的语法结构
modifier demo() {
 ...  // 函数执行前执行的代码
  _;   // 执行被修饰的函数
  ...  // 函数执行结束后执行的代码
}
```

>接口有哪些特性  
接口不能实现任何函数；  
接口无法继承其它合约，但可以继承其它接口；  
接口中的所有函数声明必须是`external`的；  
接口不能定义构造函数；  
接口不能定义状态变量；

### 07.16
- 今日学习时间：7.16  8 p.m.--10 p.m.
- 学习内容小结：Solidity 语法复习 +ether.js了解
#### receive  
用于合约接受ether，必须为`external`和`payable`属性。  
receive属于solidity默认的逻辑。  
receive不接受任何参数传入，且没有返回值。如果有参数传入，则会调用fallback函数。
*如果合约中既没有receive(),又没有fallback(),向合约中传入ether则会显示交易失败。*  
`receive() external payable{}`
#### fallback
fallback函数会在三种情况下被调用：
1. 调用者尝试调用一个合约中不存在的函数时
2. 用户给合约发Ether但是receive函数不存在
3. 用户发Ether，receive存在，但是同时用户还发了别的数据（msg.data不为空）  
`fallback（）external{}`
#### 数据编码
`abi.encode(data)`,将数据编码为字节码，以规范编程。data的数据类型可以为string，uint256等等  
`abi.decode(data,(uint256...))`，解码，data为要解码的数据，后面为要解码成的数据类型，可以解码为多种数据类型。  
`abi.encodePacked(data)`,这是一个与 abi.encode 类似但有所不同的全局函数。它也用于将参数编码为符合 ABI 标准的字节数组，但不会为每个参数添加其类型的长度信息，也不会在参数之间添加分隔符，结果是一个紧密打包的字节数组.
#### FAQ
>什么是ethers.js  
Ethers.js 是一个使用Typescript编写的库，用于构建去中心化应用程序（DApps）的前端，或者与以太坊网络进行交互。它抽象了许多复杂性，使开发人员能够简单直观地构建DApp。

### 07.17
- 今日学习时间：7.17  4 p.m.--6 p.m.
- 学习内容小结：完成 筹集合约 

### 07.18
- 今日学习时间：7.18  10 a.m.--12 a.m.
- 学习内容小结：Foundry test学校

### 什么是 Foundry
>Foundry 是一个 Solidity 框架，用于构建、测试、模糊、调试和部署Solidity 智能合约， Foundry 的优势是以 Solidity 作为第一公民，完全使用 Solidity 进行开发与测试，如果不太熟JavaScript，使用 Foundry 是一个非常好的选择，而且 Foundry 构建、测试的执行速度非常快。  
#### Foundry的主要工具:
* ***Forge*** 用来进行合约的测试
* ***Cast*** 很方便的与合约进行交互，发交易，查询链上数据
* ***Anvil*** 可以模拟一个私有节点
* ***Chisel*** 可以在命令行快速的有效的实时的写合约，测试合约

#### Foundry测试 forge test
1. 测试文件统一放在`test`包中，命名方式为`***.t.sol`
2. 测试方法的命名，是由`test_ `为前缀，后面遵循驼峰命名法。
3.  测试函数必须为`public`或`external`属性
4. 继承 `forge-std` 标准库下的 `Test.sol` 合约来编写测试用例。
	`import {Test, console} from "forge-std/Test.sol";`
	`import {Counter} from "../src/Counter.sol";`
4. 进入`test`文件，执行 `forge test` 对所有的`test`文件进行测试。
5. `forge test --match-path test/Counter.t.sol`,命令，使用`--match-path` 来指定某一路径下的文件来进行测试。
6. `forge test --match-contract CounterTest --match-test test_Increment`,命令，用 `--match-contract `来指定测试合约的名称，其中 `--match-test` 用来指定调用的测试方法。
7. `-vv`到`-vvvvv`显示由低到高等级的信息显示程度。

#### Foundry部署&验证 forge create
`forge create --rpc-url <your_rpc_url> --private-key <your_private_key> --verify src/MyContract.sol:MyContract --constructor-args <constructor_args>`
* `rpc-url`: 即区块链节点 RPC，例如：https://eth-sepolia.g.alchemy.com/v2/xxxxxxxxx
* `private-key`: 即钱包私钥，建议创建专门用来开发测试的新钱包。
* `etherscan-api-key`: 即区块链浏览器的 API KEY TOKEN，用于验证合约。
* `verify`: 验证合约，即在浏览器中开源合约的代码。
* `MyContract` : 实际部署的合约，由于一个 solidity 中允许存在多个合约，因此这里指定需要部署的合约名称。
* `constructor-args`: 合约的构造参数，如果没有，可以不设置该属性。
XXX
<!-- Content_END -->
