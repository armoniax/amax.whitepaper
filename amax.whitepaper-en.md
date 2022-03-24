# Armonia multichain blockchain platform

> Building a platform of mother-and-children chains
`v0.5`

- [Armonia multichain blockchain platform](#armonia-multichain-blockchain-platform)
  - [Introduction](#introduction)
  - [Objecives & Principles](#objecives--principles)
  - [Overall architecture](#overall-architecture)
    - [Multichain model](#multichain-model)
    - [Multichain layered architecture](#multichain-layered-architecture)
    - [Multichain transaction routing](#multichain-transaction-routing)
    - [Multichain enabled applicaiton scenariors](#multichain-enabled-applicaiton-scenariors)
    - [Cross-chain in Armonia's multichain universe](#cross-chain-in-armonias-multichain-universe)
    - [Armonia Meta Chain profile](#armonia-meta-chain-profile)
    - [Armonia meta chain consensus algorithm](#armonia-meta-chain-consensus-algorithm)
    - [Armonia-mother-chain accounts](#armonia-mother-chain-accounts)
    - [First Armonia-child-chain](#first-armonia-child-chain)
    - [Cross-chain mechanism](#cross-chain-mechanism)
  - [Tokenomics](#tokenomics)
    - [Token distribution](#token-distribution)
    - [Mining of Things (MoT)](#mining-of-things-mot)
  - [Infrasturcture support for We3](#infrasturcture-support-for-we3)
  - [xDAO governance](#xdao-governance)
  - [Technology roadmap](#technology-roadmap)
  - [Reference](#reference)
## Introduction
Looking back at the development history of blockchain technology, starting with distributed ledger, to smart contract technlogy that supports all sorts of application logic, and onto providing layer-0 & layer-1 SDK technology for quickly building brand new blockchains, and building layer-2 to solve problems that couldn't be solved in layer-1 technoloy, as well as bi-directional cross-chain technology, one can easily come to a conclusion that blockchain is becoming more sophisticated in order to fufill growing needs of decentraliazed applications aspired by blockchain users.

However, as of today, other than promoting security, reliability and decentralization, there hasn't been a single blockchain technology that can sufficiently meet the following requirements:
- massively parallel processing
- modularized and extensible
- customizable and configurable
  
Armonia's founding team believes it takes a multichain blockchain platform technology to achieve the above objectives, which thence can service every individual and business user from all around the world. It is also under Armonia's founding team's belief that the to-be-built metaverse will be a truly decentralized, open and multi-chain universe which harbors users, assets and transactions and smart-contract based etc mission critical DApps.

## Objecives & Principles
Armonia is a mother-and-children multichain blockchain platform, wherein there's Armonia Meta Chain o (`AMC`) which is the mother chain and many either homogeneous or heterogeneous Armonia Child Chains (`ACC`) that all can operate indepdently. Armonia Meta Chain is designed to be the most secure, highly performant but requiring very low to zero transaction fees. It also supports inter-blockchain brdiging for assets to be mirrowed from one to another in order to support numerous DAPPs to be built on top the platform. Under a multichain architecture, Armonia is poised to support at least one billion users worldwide.

**Core objectives**:
- To build a unified account and transaction addressing/routing system for the entire Armoina multichain universe
- `AMC` to provide a native token `$AMAX`, which will serve as the foundational value engine and trust anchor for the entire multichain based ecosystem；
- To provide layer-0 and layer-1 blockchain template implementations and SDK so as to enable rapid blockchain creation and deployment for vertical application domain specific child chains that can inter-operate with `AMC` freely for asset mirrowing and bridging;
- `ACC` chains can have their own choices and formation of consensus algorithm, virtual machine, block interval, finality and permission scope etc that determine a unique blockchain system；
- After registring and staking escrow via `AMC` chain, all distributed internet resources (including distributed file storage, computing and networking etc.) can be easily accessed and accurately metered. There'll be various onchain charging model and open markets for all web3.0 resources available throughout the Armonia network. Therefore, Armonia multichain platform can become the cornerstone of metaverse.

**Design principles**：
- Secure and reliable：It is to ensure `AMC` has a characteristic of being highly decentralized and thus anti-censorship. Any malicious activities can be timely detected, corrected and penalized, if not possible avoided. Therefor all vauluable assets onchain can be safely guarded；
- Extensible：Through modularized building blocks, Armonia blockchain system can be built like playing with legos;
- Highly performant：`AMC` can achieve 5000+ TPS and generate blocks at 1 second interval. In addition, through utilizing multiple `ACC` chains, transactions can be grouped or segerated into different `ACC` chains to further achieve sharding effect and thus massive parallel processing speed. As the total number of `ACC` chains can be infinite, the overall performce would be thus also infinite.
- Personalized: Through unique implementation in `ACC` chains, Armonia multichain platform can support infinite kinds of demands from the ecosystem that is built on top;
- Simplistic：Avoiding any form of over-design and over-implementation as long as the core objectives can be met and only through this can the entire network achieve the overall security, reliability and agility.

## Overall architecture
Armonia as a multichain platform has adopted a unique mother-children-chain model，instead of star-like models which have been adopted in other multichain technology like cosmos or polkadot：
<img src="./assets/Armonia-Multichain-Arch.png" width=800 />

**Core design**：
- `AMC` adopts an innovative consensus algorithm called `APOS` and high-performant WASM virtual machine and requires extremely low transaction cost. `AMC` also adopts account name instead of address based onchain addressing model;
- `ACC` chains can be built with layer-0 & layer-1 template modules in a very quick manner;
- Other public chains like Bitcoin or Ethereum can be also included into the multichain environment to co-exist with other `ACC` chains;
- All chains within Armonia multichain environment can mirror or bridge their assets from one to another;
  
### Multichain model

With Armonia's layer-0 and layer-1 template software and SDK, one can rapidly build many versatile child chains that can have their uniqueness in consensus algorithm, block interval, virtual machine and finality choices...etc, so that they can meet various needs from the ecosystem.

Armonia Child Chain or `ACC` can have their own native tokens or directly utilize `AMAX` which can be bridged from `AMC` chain. It is highly encouraged to implement `ACC` that runs on a gas model and utilizes `AMAX` for gas or transaction fees payment. In this way, all `ACC` chains will help to add values to `AMC` and thus the entire ecosystem.

Basically every single blockchain can be highly abstracted or characterized as a capital letter T: the horizontal line stands for all transaction and block data which will be broadcasted throughout the network; the vertical line by contrast represents the state database (which includes account balance state) that will be only constructed after execution of transactions produced from the horizontal line. Further more, dotted line circle is to represent an open and public blockchain network while solid line circle is for private blockchains）`AMC` can serve as trust anchor to all other `ACC` chains which altogehter form the following multichain universe：

<img src="./assets/Armonia-Multichain-Forest.png" title="Armonia Multichain Universe" width=800 />

### Multichain layered architecture

AS illustrated below, Armonia multichain system can be layered as follows:
<img src="./assets/multichain-layered-arch.png" width=800 />

In this design, Armonia will provide layer-0 base component to service the transcation routing capability, which means all node software can listen to a common network port for various single chains but the transcation routing component will determine whether or not the arriving transactions will be further processed in the upper layer of the node software. Through this destination chain filtering process, transactions can have one-to-one, one-to-many and one-to-all modes of accessbility to all chains within Armonia network.

Furthermore, Armonia will also provide layer-0, layer-1 template components and their corresponding SDK such that ecosystem developers can quickly implement a blockchain system by choosing the ready blockchain building blocks with personalized configurations for each chain. In so doing, all child chains can easily interact with each other.

### Multichain transaction routing

As the common building block for layer-0 in Armonia SDK, it serves to support three types of transaction routing in Armonia multichain system: 1) unicast; 2) groupcast; 3) broadcast:
<img src="./assets/tx_multichain_comm.png" width=800 />

That means, one user can intiate a blockchain transaction that can reach one single chain or a group of prescribed chains or even to every chain within Armonia multichain network. That may be helpful or even critical in a coordinated operation in the multichain network. But of course when there is any chain-level issue like lack of gas fees that could still cause the transaction execution failure, which could create an inconsistent behavior for various chains being targeted by the transaction and this problem has to be addressed rather at the application level.

<img src="./assets/tx_multichain_network.png" width=800 />

### Multichain enabled applicaiton scenariors
In Armonia's multichain empowered ecosystem, numerous application scenarios can be built including the following:
- issue, mint, transfer and exchange all sorts of crypto assets in `AMC` chain;
- build incentive mining pools in `AMC` to promote Armonia ecosystem development;
- complete KYC/KYB for `AMC` accounts in order to access those smart contracts that have regulation compilance requirements;
- create one or mulitple DEX `ACC` chains to support order-book based exchange with high-performance and low-laytency capabilities;
- create one or multiple prediction `ACC` chains to achieve both performance and privacy;
- create one or mulitple GameFi, NFT and metaverse application chains;

### Cross-chain in Armonia's multichain universe

With multiple chains co-existing in Armonia's multichain universe, there will be interaction i.e. cross-chain activities between `AMC` and `ACC` chains as well other public chains like bitcoin and ethereume. Armonia endeavors to build following cross-chain capability for blockchain users:

<img src="./assets/armonia-multichain-scope.png" title="Armonia multichain and cross-chain relationship" width=800 />


### Armonia Meta Chain profile

| Feature | Description | Memo |
|---|---|---|
| Native token | `AMAX` | issued in system contract: **amax.token** |
| Precision | 8 | the smallest unit is 1 of 100 million |
| Total supply | 1,000,000,000 | Inflate/deflate via DAO to support ecossytem advancement |
| Consenus algorithm | APOS | Armonia's DPOS |
| Virtual machine | WASM | High-performing VM |
| anti-sybil attack | resource staking and leasing model with `$AMAX`| zero gas fees | 
| Block interval | 1 sec | a fine choice between stability and transaction onchain speed |
| TPS | 5000+ | benchmarked with transfer transaction, `v1.0` |

### Armonia meta chain consensus algorithm

As the founding chain in Armonia's multichain network, `AMC` serves as the trust anchor and value engine to all other spawned child chains. For those who adopt `$AMAX` as the native token of their own chains for basic functions like transaction fees. Hence, it is crticial to ensure the security and reliability of Armonia meta chain. It means there should be a sufficient level of decentralization and anti-censoship capability as described as follows:

1. There should be enough copies of blockchain data maintained by mining nodes such that even if there were direct attacks to the mining nodes the network can still survive and operate and eventually return to a good working state;
2. When there were vicious nodes trying to sabotage the network, the activities can be discovered and even corrected as long as the total number of bad actors are below 1/3 of the total set of validators;
3. Those mining nodes can be replaced by standby nodes when they are not on their duty.

Armonia has invented a new consensus algorithm which is named as Armonia DPOS or short as APOS for `AMC` chain, the mother chain and the other child chains can adopt their own consensus algorithm to secure their network.

The constructs of APOS is as follows:
1. All network nodes that run `AMC` node software can participate in block production for both main and vice blocks that form `AMC` main and backup chain(s);
2. Those nodes that are elected through a non-stop voting process and ranked top `21` in the list become the mainnode and the rest `10,000` nodes are the backup nodes; 
3. The voting process requires the candidate nodes to stake a certain amount of `AMAX` tokens in order to receive votes from the Armonia community; 
4. The other nodes neither in the main nor backup node list are called observer nodes;
5. The main nodes take turns according to VRF algorithm to produce the main blocks and receive newly inflated `AMAX` tokens;
6. The backup nodes also take turns accoring to VRF algorithm but are applied in a much larger quorum (10,0000 nodes for one backup chain) and each backup block mined will reward the miner a certain amount of `AMAX` tokens; the backup block must refer to the latest main block being produced by the main node.
7. The main nodes shall include backup blocks during generating a main block and will be rewarded for correctly including a good bakup block;
8. When a bad backup block is included into the main block, it will not be accepted by the whole network and thus discarded by other nodes;
9. When a main blocked is missed or faulty, the backup block will repace the main block to become the actual main block and the producer node thus receives main block reward;
10. The finality of main blocks is determined through implementation of `aBFT` algorithm. However the finality of backup blocks are determined by the main blocks;
11. Transactions with main blocks must be not only verified but also executed to update the corresponding global state for the network; However, the backup blocks are only required to be verified in order to be accepted by the whole network. This way it avoids the double-spending problem and allows for the nodes to conduct parallel processing for both main and backup blocks;
12. To prevent those greedy but lazy nodes from cheating the network by producting empty or useless blocks that include useless fabricated transactions, the reward to the backup nodes for producing backup blocks will be corresponding to the simliarity of block transactions compared to those in the main blocks at the same height. Therefore, it also means the reward will be only calculated and settled in the next block height;

The interwoven main and backup `AMC` chains can have following block generation scenariors:

- In general the main and backup blocks are interwoven as following:
<img src="./assets/apos-normal.png" width=800 />

- One Armonia main node produces 6 blocks in a row before shifting to other main nodes but backup nodes shift each time after producing only one backup block:
<img src="./assets/apos-bp-nodes.png" width=800>

- If the on-duty backup node couldn't produce the block of a timeslot, the next main block won't include the backup block:
<img src="./assets/apos_vicenode_fail.png" width=800>

- If the on-duty main node couldn't produce the block of a timeslot, the next (`n+1`) main block will take the current backup block as the main block and its producing node will be rewarded with main block reward amount. However the prior (`n'-1`) backup block will be thus not rewarded as no main block is including it:
<img src="./assets/apos_mainnode_fail.png" width=800>


一主一备的双链架构下可以支持到10021个节点参与共同挖矿，维护网络健壮性和安全性，同时获得相应收益。为了进一步增加参与节点的数量，可以把一主一备双链变成一主双备甚至一主三备份这样的多链模型。每增加一条备链可以增加10000个备链挖矿节点。虽然单个备节点获得挖矿的数量少了，但是因为大大提升了网络的安全性，增强了社群的参与度和社群共识，随着币值相应上涨，单个备节点的收益反而可以保持或者进一步上涨。通过这种模型可以来激励更多的社群参与者来挖矿和建设整体网络。至于备份子链的冗余个数可以由Aarmonia的`DAO`组织来管理和决定。相应地，主备子链组合的可扩展场景如下所示：
<img src="./assets/apos_main_vice_subchains.png" width=800 />

另外考虑到自创世开始的第一年内，Armonia母链主要是核心团队在维护和开发，并不会立即对外开放投票，所以在第一年内即使维护和运行了21个超级节点，每一个挖出的块并没有任何增发奖励。在第二年随着节点投票的开始，新的节点引入之后，在满足一定的质押比例后（比如5%），每挖出的块都会有增发奖励给到该记账节点。

### Armonia-mother-chain accounts

有别于其它类似比特币、以太坊公链等采用了地址来标识用户的链上账户（通常由公钥来推导出用户地址）, Armonia母链采用了账户模型，账户绑定了一个或者多个公钥，并且需要用户提前注册好才能使用。Armonia母链规定所有的账户都由一个唯一名称来标识，名称的最大长度为12个字符（[`1-5`,`a-z`,`.`]), 未来可以扩展到24字符([`1-9`,`a-z`,`.`,`#`,`@`])。该名称由帐户的创建者指定。帐户创建者必须使用 `$AMAX`代币预留一定的RAM数值用来存储新帐户，直至新帐户质押自己的代币来预留自己的RAM。

在去中心化的背景下，应用程序开发人员在新用户注册时，会象征性地支付账户创建费用。传统企业为获取客户，已经以广告、免费服务等形式为每个用户花费了大量资金。相比之下，创建新的区块链账户所需的资金成本微不足道。不过好在如果用户在注册另一个应用程序时已经创建了帐户，那就没有必要再次创建了。


### First Armonia-child-chain
考虑到和世界上目前最流行的以太坊区块链技术的兼容，Armonia的第一条子链采用以太坊的底层核心技术，包括EVM虚拟机和地址模型等，具体特征如下：
| 特征 | 说明 | 备注 |
|---|---|---|
| 原生代币符号 | `AMAX` | 由母链跨链而来 |
| 共识机制 | PoSA |  |
| 虚拟机 | EVM | 高性能虚拟机 |
| 防女巫攻击 | 交易需要消耗Gas，即支付`$AMAX` | 根据实际gas数量和价格的乘积来决定 |
| 账户模型 | 地址模型 | 格式：`0x...` |
| 出块速度 | 3 秒 | |
| TPS | 160+ | 基准测试为转账交易，`v1.0`即实现目标 ｜

### Cross-chain mechanism

在一个多链的生态体系里面，可以让链上发行的资产从原链映射到另外一条链或者反之是至关重要的。某种意义上讲，跨链增加了链上资产的流动性和可用性。同时，将一个资产从原链跨到另外一条链，也可以自由跨链回来，可以满足资产用户的在区块链生态内的全部需求。

但是要做到以上的双向、可靠、高效的跨链，需要解决跨链过程中涉及到的各类问题：
- 如何保障链上资产转移交易的最终确定性
- 如何把一条链的交易信息及时同步到另外一条链上去
- 如何确保跨链中各项交易执行内容的准确性和有效性
- 如何避免恶意用户利用跨链盗走资产
- 如何防止在映射的链上面的映射资产被恶意滥发并使用
  
同时还需要考虑的问题有：如何实现一种通用性的跨链解决方案，可以满足各种链之间的跨链需求，而不是为不同链定制不同跨链方案。

Armonia核心团队基于以上问题，提出了一种混合治理模型的且相对安全可靠的通用型跨链解决方案，具体如下：

说明：
| 名称 | 代号 | 
| ---- | ---- |
| Armonia母链 | `M` |
| 跨链资产所在原链 | `A` |
| 跨链资产映射目标链 | `B` |
| 跨链用户 | `BU` |
| 跨链服务商 | `BO` |
| 跨链目标资产 | `AS` |
| 跨链目标资产在目标链的治理组织 | `DAO` |

资产在A链上的分配已经由A链的共识机制、通证经济和生态发展决定了，跨链的资产在目标链B上面需要有相应的ERC20合约来承载，提供铸币、发行、转账和销毁等功能，并且这些功能由DAO来决定。

* 准备工作
1. 在M链上提供系统合约作为跨链的基础合约`amax.xswap`，记录和管控跨链同类资产兑换的全部过程；
2. 在A链部署部署合约作为跨链资产的托管合约`as_custody`；
3. 在B链部署ERC20合约`as_erc20`作为资产接收和销毁功能；同时也有动态铸币功能，铸币权由DAO来管控；

* 流程如下
1. BO找到DAO，申请在B链上的跨链资产，比如说100万枚AS；DAO在BO打入100万A链上的资产到`as_custody`,在B链上通过`as_erc20`合约铸币100万AS给BO；
1. BO开始通过`amax.xswap`上面挂上出售的订单，并且质押两倍价值的AMAX代币在该合约内；
1. BU通过`amax.xswap`找到自己愿意成交的订单，可以部分或者全部吃下该订单；
1. BU将AS资产从A链打入到BO的账户或者地址；同时将该交易`TxID`通知到`amax.xswap`的订单状态内；
1. BO在得到订单状态变更后将相应的AS资产在目标链B打入到BU的地址或者账户上，从而完成订单；
   
注：
1. 如果兑换订单产生纠纷，将由`DAO`来帮助完成仲裁过程，确保订单的正确执行或关闭；
2. 母链M也可能是A链或者B链之一。

流程示意图如下：

<img src="./assets/armonia-cross-bridge-cn.png" width=800 />

## Tokenomics

Armonia的母链发行了`$AMAX`的原生代币，不光用于母链的运作所需资产，也可以为子链运行所需，甚至成为它们的原生代币。特别是由Armonia核心团队主导的子链都将采用`$AMAX`作为子链运行所需的原生代币。

`$AMAX`的设计发行总量最大值为210亿枚，但是第一阶段的设计发行量为10亿枚，并且只有实际可流通市值在100倍增长的前提下，DAO组织才考虑增发的可能性。


### Token distribution

`$AMAX`的总量分配如下：
<img src="./assets/amax-total-allocation.png" width=800 />

其中, 市场募资使用`$AMAX`占总量的15%, 用来实现以下2个核心目的：
- Armonia核心团队的项目建设所需经费来源
- 释放足够的币到市场流通，允许参与竞选挖矿的节点的质押币和投票的币能够满足5%的总体质押量来激活挖矿。

市场募集份额里面又分2%的种子轮私募，3%的机构私募，和剩余10%的去中心化发行IDO。并且采用和系统质押总数成正比的Bonding curve的公式来决定`$AMAX`的动态价格。另外凡是私募的都有锁仓机制，确保市场有足够的时间运行Armonia全方位生态应用建和价值建设起来。

其次，10%的币量用于基金会，主要在市值管理和长期发展去中心化自助组织所用。其代币将存放于`amax.fund`账户，由Armonia核心团队多签管理，可以接受市场的整体监督，确保用于有助于生态发展的地方。

最后，占75%的币量将用于生态内的各类挖矿，在Armonia称为万物即挖矿。

### Mining of Things (MoT)
在Armonia的生态建设理念里，凡是对生态做出了某种贡献的，增加了整体价值的，都可以称为挖矿的行为，必定有相应的收益激励。

总体上从大的方面讲，有以下挖矿的方式存在：
|挖矿种类|分配比例|挖矿说明|
|---|---|---|
|公链建设挖矿 - 早期阶段 | 15% |由早期的核心团队领导完成公链的`v1.0`, `v2.0`和`v3.0`的里程碑建设|
|公链建设挖矿 - 后期阶段 | 15% |由建设而成的开发者DAO全面驱动的公链技术和生态应用的发展|
|主节点挖矿 | 5% | 30月减半机制，运行12月后改成：5年减半机制| 
|从节点挖矿 | 5% | 30月减半机制，运行12月后改成：5年减半机制|
|Web3挖矿 | 10% | 为服务和建设web3应用体系而激励生态内的相应挖矿激励 |  
|生态建设挖矿| 25% | 其它凡是有利于生态建设的各类短期或者周期性的挖矿激励 |

其中生态挖矿包括但是不限于以下类型：
- 注册邀请用户加入
- 提供KYC、KYB的供应商的服务
- 提供预言机服务的行为
- 从第三方公链把主流资产跨链过来的行为

## Infrasturcture support for We3
要建设Web3，意味着很多中心化下的互联网的基础服务都可以在去中心化的方式下提供出来，并通过代币结算被满足应用层需求的各项基础设施服务。

Web3的去中心化服务建设包括但是不限制于以下类型：
- DFS：去中心化文件存储服务
- DCOMP：去中心化的计算服务（例：租用虚拟机后部署容器并运行一段时间的服务）
- DNET：去中心化网络服务，包括流量分发，路由服务等
- DCDN：去中心化的CDN服务
- DDNS：去中心化的域名解析服务
- DID：去中心化的身份认证服务

如果有效地衡量以上基础服务的贡献，并相应用`$AMAX`来激励，是Armonia支持web3需要解决的一个课题。

## xDAO governance
在去中心化的世界里面，技术、产品还有整个生态的发展，有很多需要优化改进的地方，这都需要有一个链下治理决策然后完成链上升级变更的过程。但是这种治理必须同样符合去中心化理念，是由社区利益相关者积极参与，通过链上投票完成各项提议复议，最后执行的过程。

因此有必要建设Armonia的各项去中心化自助组织DAO来驱动整个区块链技术、应用和生态建设和长期发展。并且我们需要有一个顶级的DAO组织来管理下级的各类DAO组织来驱动各项建设，我们把这个称为`Armonia xDAO`。

基本流程如下：

<img src="./assets/amax_dao_process.png" width=800 />

- 其中DAO智能合约由相应DAO组织来实现部署，并开放源码给到DAO组织里面的成员；
- DAO组织里面的成员也需要通过一个招募的过程完成，并通过DAO合约发行的凭证代币获得投票资格；
- DAO成员的投票数量根据DAO合约协议相应发放；
- DAO组织里面的成员都可以进行某个事项的提议，包括完成复议的奖励金额提议，可以是个人提供也可以是DAO组织提供
- DAO成员参与复议投票，可以有具体的投票截止时间，按照一币一票等规则；
- 计票后根据该轮选择的决策规则，来判定提议是否通过；
- 如果提议通过，则通过指定的执行人来完成提议的执行；
- DAO组织最后检查执行结果并完成该提议的最终状态为结束
  
Armonia里面的一些基本DAO有如下：
- 开发者DAO：负责公链开发驱动，包括功能提议实现修改和发布，并提供激励和审核机制；
- 节点DAO：负责挖矿节点之间的协调，整个区块链网络的安全保障议题事项的落实，备链挖矿的决议等；
- AMAX代币DAO：AMAX的发行和分配、机制；
- 万物挖矿：包括各项新的矿池的开设和关闭、激励来源和执行；
  
## Technology roadmap

Technology roadmap:
- v1.0：实现多链系统的母链和第一条EVM子链的搭建和部署，母链实现APOS共识机制，双向跨链实现;
- v2.0：实现生态内开放式的web3资源共享挖矿机制和相应web3的访问技术对接;
- v3.0：实现多链的L0-base，L0, L1的模块化和模板化SDK，可以快速搭建生态内各类单链.

在实现v3.0之后的技术路线图，必将由`developer dao`来全面驱动和治理实现完成。

## Reference
- metaverse: https://theconversation.com/the-metaverse-is-money-and-crypto-is-king-why-youll-be-on-a-blockchain-when-youre-virtual-world-hopping-171659
- DPOS: https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper
- aBFT: https://hedera.com/learning/what-is-asynchronous-byzantine-fault-tolerance-abft
- VRF: https://en.wikipedia.org/wiki/Verifiable_random_function
- DAO: https://consensys.net/blog/blockchain-explained/what-is-a-dao-and-how-do-they-work/
- finality：https://academy.binance.com/en/glossary/finality