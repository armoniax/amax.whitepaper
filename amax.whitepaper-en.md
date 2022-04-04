# Armonia multichain blockchain platform

> Building a mother-and-child multichain blockchain platform
`v0.5`

- [Armonia multichain blockchain platform](#armonia-multichain-blockchain-platform)
  - [Introduction](#introduction)
  - [Objectives & Principles](#objectives--principles)
  - [Overall Architecture](#overall-architecture)
    - [Multichain Model](#multichain-model)
    - [Multichain Layered Architecture](#multichain-layered-architecture)
    - [Multichain Transaction Routing](#multichain-transaction-routing)
    - [Multichain Enabled Application Scenarios](#multichain-enabled-application-scenarios)
    - [Cross-Chain in Armonia's Multichain Universe](#cross-chain-in-armonias-multichain-universe)
    - [Cross-Chain Mechanism](#cross-chain-mechanism)
  - [Armonia Meta Chain](#armonia-meta-chain)
    - [Basic Profile](#basic-profile)
    - [Consensus Algorithm](#consensus-algorithm)
    - [Account](#account)
  - [The First Armonia-Child-Chain](#first-armonia-child-chain)
  - [Tokenomics](#tokenomics)
    - [Token Distribution](#token-distribution)
    - [Mining of Things (MoT)](#mining-of-things-mot)
  - [Infrastructure Support for Web3](#infrastructure-support-for-web3)
  - [xDAO Governance](#xdao-governance)
  - [Technology Roadmap](#technology-roadmap)
  - [Core Team](#core-team)
  - [Reference](#reference)
## Introduction
To address growing user application needs, blockchain technology has evolved from distributed ledger, to smart contract technology that supports all sorts of application logic, through to providing layer-0 and layer-1 SDK technology that facilitates rapid building of new blockchains, and building layer-2 to solve problems that couldn't be solved with layer-1 technology, as well as bi-directional cross-chain technology.

However, other than promoting security, reliability and decentralization, there hasn't to-date been a single blockchain technology that can sufficiently meet the following requirements:
- massively parallel processing;
- modularized and extensible; and
- customizable and configurable
  
Armonia's founding team believes it takes a multichain blockchain platform technology to achieve the above objectives, which can then service every individual and business user globally. It is also Armonia's founding team's belief that the to-be-built metaverse will be a truly decentralized, open and multi-chain universe which harbors users, assets, transactions and smart-contract based, mission-critical DApps.

## Objectives & Principles
Armonia is a mother-and-child multichain blockchain platform, wherein Armonia Meta Chain (`AMC`) is the mother chain to all other sovereign Armonia Child Chains (`ACC`). AMC is designed to be highly secure and highly performant chain with very low or even zero transaction fees. It also supports inter-blockchain bridging and mirroring of assets capable of supporting numerous DAPPs to be built on top of the platform. Under a multichain architecture, Armonia is poised to support at least one billion users worldwide.

**Core Objectives**
- To build a unified account and transaction addressing/routing system for the entire Armonia multichain universe;
- `AMC` will issue a native token `$AMAX`, which will serve as the foundational value engine and trust anchor for the entire multichain based ecosystem;
- To provide layer-0 and layer-1 blockchain template implementations and SDK which enables rapid blockchain creation and deployment for vertical application domain specific child chains that can inter-operate with `AMC` freely for asset mirroring and bridging;
- `ACC` chains can be homogeneous chains or heterogeneous chains, public chains, private chains or alliance chains, etc., which can have their own choices and formation of consensus algorithm, virtual machine, block interval, finality and permission scope, etc. that determine a unique blockchain system;
- After registering and staking escrow via the `AMC` chain, all distributed Internet resources (including distributed file storage, computing and networking, etc.) can be easily accessed and accurately metered. There will be various onchain charging models and open markets for all Web3.0 resources available throughout the Armonia network. The Armonia multichain platform can therefore become the cornerstone of the metaverse.

**Design Principles**
- Secure and reliable: to ensure `AMC` has a characteristic of being highly decentralized. Any malicious activities can be detected, corrected and penalized, if not avoided on a timely basis. Therefore, all assets onchain can be truly safe guarded；
- Extensible: through modularized "lego-style" building blocks, Armonia's blockchain system can be combinable, replaceable and extendable;
- High performance: `AMC` can achieve 5000+ TPS and generate blocks at 1 second intervals. In addition, through utilizing multiple `ACC` chains, transactions can be grouped or segregated into different `ACC` chains to achieve sharding effects and acquire massive parallel processing speeds. As the total number of `ACC` chains can be infinite, the overall performance would thus also be infinite.
- Personalized: the characteristics of the `ACC` chains can be tailored, whereby Armonia's multichain platform can support infinite kinds of demands from the over-laying ecosystem; and
- Simply: Armonia's multichain platform avoids any form of over-design or over-implementation to ensure the entire network maintains its overall security, reliability and agility.

## Overall Architecture
As a multichain platform, Armonia has adopted a unique mother-and-child-chain model, as compared to the star-like models which have been adopted in many other multichain technologies like Cosmos or Polkadot:
<img src="./assets/Armonia-Multichain-Arch_en.png" width=800 />

**Core Design**
- `AMC` adopts an innovative consensus algorithm called `APOS` and high-performance WASM virtual machine, requiring extremely low transaction cost. `AMC` also adopts an account name rather than an address based onchain addressing model;
- `ACC` chains can be rapidly built with layer-0 and layer-1 template SDK modules and can be either homogeneous or heterogeneous;
- Other public chains like Bitcoin or Ethereum can also be included in the multichain environment to co-exist with other `ACC` chains; and
- All chains within the Armonia multichain environment can mirror or bridge their assets from one to another.
  
### Multichain Model

With Armonia's layer-0 and layer-1 template software and SDK modules, users can rapidly build many versatile child chains with their uniqueness in consensus algorithm, block interval, virtual machine and finality choices, etc., to meet the various needs of the ecosystem.

`ACC` use have their own native tokens or directly utilize `$AMAX` which can be bridged from the `AMC` chain. It is highly encouraged to implement `ACC` that runs on a gas model and utilizes `$AMAX` for gas or transaction fee payment. By increasing the demand of $AMAX, `ACC` will help to add value to `AMC`, and even the entire ecosystem.

Basically, every single blockchain can be highly abstracted or characterized as the capital letter "T" whereby the horizontal line stands for all transaction and block data broadcasted throughout the network and the vertical line represents the state database (for example, account balance state) that is only constructed after execution of transactions produced from the horizontal line. Furthermore, a dotted line circle is used to represent an open and public blockchain network while a solid line circle represents a private blockchain. `AMC` can serve as trust anchor to all other `ACC` chains which collectively form the following multichain universe:

<img src="./assets/Armonia-Multichain-Forest_en.png" title="Armonia Multichain Universe" width=800 />

### Multichain Layered Architecture

Armonia multichain system can be layered as follows:
<img src="./assets/multichain-layered-arch.png" width=800 />

In this design, Armonia will provide layer-0 base components to service the transaction routing capability, which means all node softwares can acquire information from a common network port for various single chains but only the transaction routing components can determine whether or not the arriving transactions will be further processed in the upper layer of the node software. Through this destination chain filtering process, transactions can have one-to-one, one-to-many and one-to-all modes of accessibility to all chains within the Armonia network.

Furthermore, Armonia will provide layer-0, layer-1 template components and their corresponding SDK modules so that ecosystem developers can quickly implement a blockchain system by choosing the ready blockchain building blocks with personalized configurations for each chain. In doing so, all child chains are able to easily interact with each other.

### Multichain Transaction Routing

As the common building block for layer-0 in the Armonia SDK module, it serves to support three types of transaction routing in the Armonia multichain system: 1) unicast; 2) multicast; 3) broadcast:
<img src="./assets/tx_multichain_comm_en.png" width=800 />


This means that one user can intiate a blockchain transaction that can reach a single chain or a group of prescribed chains or even every chain within Armonia multichain network. This routing capability can be useful or even critical when undertaking some coordinated operations in the multichain network. Notwithstanding the foregoing, when there's a chain-level issue such as lack of gas fees that causes transaction failure, some inconsistencies among chains could thus be incurred. This problem can be easily addressed at an application level. Similarly, resending a transaction multiple times just to ensure its delivery shall cause no harm onchain due to the idempotency nature of tranasactions. 
<img src="./assets/tx_multichain_network.png" width=800 />

### Multichain Enabled Application Scenarios
In Armonia's multichain empowered ecosystem, numerous application scenarios can be built, including the following:
- issue, mint, transfer and exchange all sorts of crypto assets in the `AMC` chain;
- build incentive mining pools in `AMC` to promote Armonia ecosystem development;
- complete KYC/KYB for `AMC` accounts in order to access smart contracts that have regulatory compliance requirements;
- create one or multiple DEX `ACC` chains to support order-book based exchanges with high-performance and low-latency capabilities;
- create one or multiple prediction `ACC` chains to achieve both performance and privacy; and
- create one or multiple GameFi, NFT and metaverse application chains;

### Cross-Chain in Armonia's Multichain Universe

With multiple chains co-existing in Armonia's multichain universe, there will be interaction (i.e. cross-chain activities between `AMC` and `ACC` chains and other public chains like Bitcoin and Ethereum). Armonia endeavors to build the following cross-chain capabilities for it's blockchain users:

<img src="./assets/armonia-multichain-scope_en.png" title="Armonia multichain and cross-chain relationship" width=800 />


### Cross-Chain Mechanism


In Armonia's multichain universe, the ability of "moving" an asset from one chain to another can be critical for asset owners. If the originating asset resides in its home chain where the asset is issued from, "moving" the asset means locking an asset in the originating chain and minting the assets from the destination chain and transferring the assets to the designated account. However, if the originating asset resides in a non-native chain, "moving" the asset means destroying or burning the asset from the originating chain, unlocking the asset and sending the designated account from the home chain to the asset. This two-way moving activity that happens between any two chains within Armonia's multichain universe are cross-chain transactions. 


Through cross-chain transactions, asset owner can move an asset from one chain to another, which greatly increases the liquidity and usability of the asset. This flexibility can help satisfy all kinds of application scenarios that happen in the entire ecosystem.

However, the following problems must be solved to achieve bi-directional, reliable and efficient cross-chain transactions:
- how to ensure the finality of the asset-moving transaction onchain?
- how to synchronize the asset transferring or locking result from one chain to another?
- how to ensure transactions involved in cross-chain workflow are effective and accurate as expected?
- how to prevent malicious users from stealing the assets during the cross-chain transactions?
- how to prevent the mirroring asset from being overly inflated?
  
At the same time, one important question that remains to be answered is:
How to establish a simple-to-use and unified cross-chain solution that can work with all kinds of blockchain in Armonia's multichain universe?

In addressing the above problems, one hybrid and reliable cross-chain solution has been proposed as follows:

**Legend**:
| Item | Symbol | 
| ---- | ---- |
| Armonia Meta Chain | `M` |
| Asset originating chain | `A` |
| Asset destination chain | `B` |
| Cross-chain user | `BU` |
| Cross-chain operator | `BO` |
| Cross-chain asset | `AS` |
| DAO for asset-mirrored chain | `DAO` |

Note: Distribution of assets from chain `A` has been determined by its consensus mechanism, tokenomics and ecosystem. However, for an asset to be mirrored to its destination chain `B` it must be managed within an `ERC20` token contract for its issuing, minting, transferring, burning, etc. and these activities will be governed by its `DAO` body.

* Preparation work
1. Deploy a smart contract `amax.xswap` onto chain `M`  for cross-chain management;
2. Deploy a smart contract `as_custody` onto chain `A`  to lock cross-chain assets; and
3. Deploy a smart contract `as_erc20` onto `B` for issuing, minting and destroying mirrored assets, governed by its DAO.

* Workflow
1. `BO` approaches `DAO`, requests bridging assets from `B`, say 1 mn `AS`, and sends them into `as_custody`. Then, `DAO` mints 1 mn AS from `as_erc20` and transfers them to `BO`;
2. `BO` places orders on `amax.xswap` with `$AMAX` as escrow that is locked into the same contract;
3. `BU` finds the orders they want to take from `amax.xswap` and they can either take the orders partially or entirely;
4. `BU` sends `AS` from chain `A`  to `BO`'s account and posts its transaction ID to `amax.xswap` as payment proof; and
5. `BO` sends `AS` from chain `B`  to `BU`'s account upon notification of order status change and closes the order upon `BU`'s confirmation;
   
Note:
1. When there's any dispute about swap orders, `DAO` will be involved to do the arbitrage to ensure the complete closure of the orders;
2. `AMC` can also be `A` or `B` chain.

The detailed workflow diagram:

<img src="./assets/armonia-cross-bridge_en.png" width=800 />

## Armonia Meta Chain

### Basic Profile

| Feature | Description | Notes |
|---|---|---|
| Native token | `$AMAX` | Issued in system contract: **amax.token** |
| Precision | 8 | The smallest unit is 1 of 100 million |
| Total supply | 1,000,000,000 | Inflate/deflate via DAO to support ecosystem advancement |
| Consensus algorithm | APOS | Armonia's DPOS |
| Virtual machine | WASM | High-performing VM |
| Anti-sybil attack | resource staking and leasing model with `$AMAX`| Zero gas fees | 
| Block interval | 1 sec | A fine choice to balance stability and transaction onchain speed |
| TPS | 5000+ | Benchmarked with transfer transaction, `v1.0` |

### Consensus Algorithm

As the founding chain in Armonia's multichain network, `AMC` serves as the trust anchor and value engine to all the other spawned child chains. For those who adopt `$AMAX` as the native token of their own chains for basic functions like paying transaction fees, it is critical to ensure the security and reliability of the Armonia meta chain. This means sufficient decentralization and anti-censorship capability is required, as follows:

1. There should be enough copies of blockchain data maintained by mining nodes so that even if the mining nodes are under direct attack, the network can survive, operate and eventually return to a stable working state;
2. When there are vicious nodes trying to sabotage the network, the activities can be discovered and even corrected - as long as the total number of bad actors is below 1/3 of the total set of validators; and
3. Those mining nodes can be replaced by standby nodes when they are off-duty.

Armonia has developed a new consensus algorithm, known as Armonia DPOS (or, shortened to `APOS`), for the `AMC` chain, the mother chain and the other child chains can adopt their own consensus algorithm to protect their network.

The core framework of APOS is as follows:
1. All network nodes that run `AMC` node software can participate in block production for both main and blocks that form `AMC` main and backup chain(s);
2. The nodes elected through a non-stop voting process and rank top `21` in the list become the main nodes and the remaining `10,000` nodes are the backup nodes; 
3. The voting process requires the candidate nodes to stake a certain amount of `$AMAX` tokens in order to receive votes from the Armonia community; 
4. The other nodes either in the main or backup node list are called observer nodes;
5. The main nodes take turns according to VRF algorithm to produce main blocks and receive newly inflated `$AMAX` tokens;
6. The backup nodes also take turns according to VRF algorithm but are applied in a much larger quorum (10,000 nodes for one backup chain) and each backup block mined will reward the miner with a certain amount of `$AMAX` tokens. The backup block must refer to the latest main block being produced by the main node;
7. The main nodes shall include backup blocks when generating a main block and will be rewarded for correctly including a good backup block;
8. When a bad backup block is included in the main block, it will not be accepted by the whole network and thus discarded by other nodes;
9. When a main block is missing or faulty, the backup block will replace the main block to become the actual main block and the producer node thus receives the main block reward;
10. The finality of main blocks is determined through implementation of an `aBFT` algorithm. However, the finality of backup blocks is determined by the main blocks;
11. Transactions with main blocks must be not only verified but also executed to update the corresponding global state of the network, while the backup blocks are only required to be verified in order to be accepted by the whole network. In this way, it avoids the double-spending problem and allows for the nodes to conduct parallel processing for both main and backup blocks; and
12. To prevent greedy or lazy nodes from cheating the network by producing empty or useless blocks that include useless fabricated transactions, reward to the backup nodes for producing backup blocks will correspond with the similarity of block transactions compared to those in the main blocks at the same height. Therefore, the reward will only be calculated and settled in the next block height.

The interwoven main and backup `AMC` chains may have the following block generation scenarios:

- In general the main and backup blocks are interwoven as follows:
<img src="./assets/apos-normal.png" width=800 />

- One Armonia main node produces 6 blocks in a row before shifting to other main nodes. But backup nodes shift each time after producing only one backup block:
<img src="./assets/apos-bp-nodes.png" width=800>

- If the on-duty backup node is unable to produce the block of a timeslot, the next main block won't include the backup block:
<img src="./assets/apos_vicenode_fail.png" width=800>

- If the on-duty main node is unable to produce the block of a timeslot, the next (`n+1`) main block will take the current backup block as the main block and its producing node will be rewarded with the amount of the main block reward. However, the prior (`n'-1`) backup block won't be rewarded as no main block is included:
<img src="./assets/apos_mainnode_fail.png" width=800>

To summarize, the `AMC` chain can be composed of one main chain and zero to several backup chains that includes in total `21 + 10,000 * n` number of mining nodes. Unlike a pure DPOS consensus algorithm that rewards candidate nodes that don't run the node software, APOS only rewards those that run the node software, synchronize with the network and actually produce main or backup blocks. This way, it greatly improves the overall security of the `AMC` chain.

With more backup nodes to participate, even though each backup node might get a reduced chances to mine blocks and thus mine fewer `$AMAX`, the overall network security and community consensus is enhanced and will eventually enchance the `$AMAX` token value. This will encourage more users to participate and further increase the awareness of the project. As for the number of backup chains, it can be decided by DAO governance mechanism.

The following diagram depicts what `AMC` will look like with the number of backup chains increasing:
<img src="./assets/apos_main_vice_subchain_en" width=800 />

Voting for mining node election will not start during the first year of its inception as the `AMC` chain will be undergoing a fast-pace development and will likely upgrade its mode. Therefore, the original 21 main nodes will not yield any new `$AMAX` token upon each block production. Voting is expected to be open to the public after passing `v1.0` milestone and new tokens will be minted/inflated after all staked and voted `$AMAX` tokens reach more than 5% of the total supply.

### Account

Rather than utilize a public-key derived address to denote each account, `AMC` adopts an account model based on an account name. One account can be bound from one or multiple public keys and the key requires its owner to register/activate it before any transaction can be made within the account. Each account name is composed of 12 alphanumeric characters ([`1-5`,`a-z`,`.`]) and can be extended to support 24 such characters ([`1-9`,`a-z`,`.`,`#`,`@`]). To participate in all kinds of transactions, account owners must stake a certain amount of `$AMAX` tokens to reserve a certain amount of system RAM, CPU, network and other resources.

## First Armonia-Child-Chain
To embrace the largest crypto ecosystem in the current world, Armonia's first child chain will stay 100% compatible with Ethereum and their cloned chains. Its main features include:

| Feature | Description | Memo |
|---|---|---|
| Native token | `$AMAX` | Bridged from `AMC` chain |
| Consensus algorithm | PoSA |  |
| Virtual machine | EVM | support solidity language for its smart contract development |
| Anti-sybil attack | Gas fees, paid in `$AMAX` | `Gas fees = Gas amount x Gas price` |
| Account model | public key derived addresses | Format: `0x...` |
| Block interval | 3 seconds | |
| TPS | 160+ | Benchmarked with transfer transactions, `v1.0` ｜


## Tokenomics

The Armonia meta chain has its native token `$AMAX` which is not only a source of power to all activities on `AMC` but can also serve child chains and even become their native token when chosen so by the child chains.

The total supply of `$AMAX` is 1 billion and there won't be any systematic inflation. Armonia `DAO` can decide whether to implement inflation to `$AMAX` for the success of the ecosystem.


### Token distribution

The overall allocation of `$AMAX` tokens are as follows:

<img src="./assets/amax-total-allocation_en.png" width=800 />

* Market sales allocation
  
 `$AMAX` tokens to be used for market sales occupy 15% of the total issued amount, which will serve the following purposes:
 * Support the project development by Armonia's core team and the `DAO` body; and
 * Use to mine node staking and voting to allow 5% staking ratio for mining activation.

Of the aggregate 15% allocated to market sales, 2% is expected to be allocated to seed investors, 3% to institutional investors and 10% for an `IDO` which will use a bonding curve formula to bind the `$AMAX` price with the total staking amount.

* Armonia Foundation allocation

To support the overall health of the market capital and `DAO` development, 10% of `$AMAX` will be allocated to the Armonia Foundation and kept in the `amax.fund` which can be supervised by the entire community and will only be used for the advancement of the ecosystem.

* Mining allocation

In total, 75% of `$AMAX`'s total supply will be used for mining activities within Armonia's ecosystem and is regarded as "mining of things", meaning all value contributing to activities in the ecosystem can take the form of mining and participants can be rewarded with tokens including `$AMAX'.

### Mining of Things (MoT)

It is in Armonia's belief that every value-added activity within the Armonia ecosystem and community shall be rewarded. Mining to be conducted in smart-contract based mining pools is a good mechanism to support the activities.

In general, the following types of mining pools exist:
|Mining category|Mining Ratio (`$AMAX`)| Description |
|---|---|---|
|Blockchain development mining | 30% |15%: for achieving milestone development: `v1.0`, `v2.0` and `v3.0`; Afterwards, 15%: `DAO` driven development |
|Main-blocks mining | 5% | Halving every 30 months | 
|Backup-blocks mining | 5% | Ditto |
|Web3 mining | 10% | To reward those who provide web3 resources |  
|Ecosystem development mining| 25% | Any other beneficiary activities to the ecosystem development |

The ecosystem development mining activities include but are not limited to the following:
- Registration of accounts and invitation to other users to register their accounts;
- Provide KYC/KYB service and verify the accounts onchain;
- Provide other kinds of oracle services; and
- Transfer main assets from other well-known blockchains.

## Infrastructure Support for Web3
To achieve Web3, a host of internet services can be built and offered in a decentralized manner as well as metered and compensated with crypto tokens.

Web3 enabling services include but are not limited to the following:
- DFS: Decentralized File Storage
- DCOMP: Decentralized Computing Resources (e.g. VM leasing for application running)
- DNET: Decentralized Networking, including traffic distribution/forwarding and routing, etc.
- DCDN: Decentralized CDN Service
- DDNS: Decentralized DNS Service
- DID: Decentralized Identity Service

Armonia'score team endeavors to build the above list of decentralized Web3 services by effectively metering the health and usage of services with `$AMAX` as the main token to incentivize all contributors to Web3 enablement.

## xDAO Governance
In a world of decentralization, technologies and products need to be constantly discussed and improved, and the entire community needs to interact in order to decide how to appropriately incentivize those who contributes and if possible, to penalize those who seek to damage or otherwise cause harm to the ecosystem. This requires that both onchain and offchain activities take place in an orchestrated manner. It is of paramount importance to make sure this type of governance adheres to the decentralization principle by getting all stakeholders within the ecosystem to freely participate by making proposals, voting/approving the proposal and executing both onchain and offchain.

Therefore, it is necessary to establish a decentralized autonomous organization or `DAO` to drive the overall development of the Armonia ecosystem by steering the technology development and propelling community growth. As there can be an infinite number of topics, projects and efforts led by `DAO` bodies, there may also be interactions between these `DAO` bodies to achieve consensus on common topics or objectives. Hence, a top-level `DAO` that leads all sub-level `DAO` bodies will be very important in guiding the development of `DAO` bodies. The top `DAO` is named as `Armonia xDAO`.

For a `DAO` body, the common governance workflow is as follows:

<img src="./assets/amax_dao_process_en.png" width=800 />

- `DAO` body deploys the smart contract which is open sourced to all participants;
- Members of `DAO` may be recruited through a certain process and registered with the `DAO` body but the public may also be able to participate in the management activities;
- Members may be distributed with voting tokens according to the governance protocol;
- Any member within a `DAO` body can make proposals for particular subjects and allocate funds to reward those who help fulfill the objectives. The funds may come from the member himself or from the `DAO` treasury reserve;
- All members can vote for the proposals and the voting period is time-controlled. The vote can be one-account-one-vote or one-token-one-vote based;
- For computing/determining if the proposal or issue is passed, there can be equal vote, weighted vote, median vote, etc. types;
- If the proposal is passed, the pre-designated account or member may be required to execute the proposal; and
- The `DAO` body may review and confirm the execution result.
  
The following basic `DAOs` will be founded:
- Developer DAO:  guides the blockchain technology development, including blockchain feature upgrade and bug fix, with pre-allocated incentive tokens to reward the contributors;
- Miner DAO: once `AMC` chain has been activated for inflation, each mined block will contain a certain amount of inflated `$AMAX` tokens to reward the miners. The miners DAO will coordinate among the miners to ensure network security (e.g. how many backup chains shall be supported to include as many miners as possible);
- AMAX DAO: to govern the issuance, minting and burning of `$AMAX` tokens; and
- `MoT` DAO: Mining of Things governance body to determine what mining pools shall be created, how to reward the miners, etc.
  
## Technology Roadmap

Technology roadmap:
- v1.0: Armonia meta chain (WASM based) and the first child chain (EVM based) successfully launched, with the meta chain supporting `APOS` consensus algorithm and providing two-way cross-chain ability between `AMC` and the first child chain;
- v2.0: enable Web3.0 resource mining and provide SDK for interfacing with Web3 resources; and
- v3.0: provide layer0-base, layer-0, layer-1, etc. template implementation to enable rapid blockchain development;

Note: After Armonia `v3.0` has been achieved, all development will be driven by the `developer DAO`.

## Core Team

A world-class blockchain research and development team with many years of experience in the blockchain industry. With in-depth participation in the research and development of multiple public blockchain projects, the team can quickly refine and integrate new technologies. 

The operation team has in-depth experience in the cultural copyright transaction system, and has also independently developed different e-commerce models under the different business scenarios. The experience equipped the team with ability to better integrate traditional finance with the Armonia ecosystem and innovate. 

## Reference
- metaverse: https://theconversation.com/the-metaverse-is-money-and-crypto-is-king-why-youll-be-on-a-blockchain-when-youre-virtual-world-hopping-171659
- DPOS: https://steemit.com/dpos/@dantheman/dpos-consensus-algorithm-this-missing-white-paper
- aBFT: https://hedera.com/learning/what-is-asynchronous-byzantine-fault-tolerance-abft
- VRF: https://en.wikipedia.org/wiki/Verifiable_random_function
- DAO: https://consensys.net/blog/blockchain-explained/what-is-a-dao-and-how-do-they-work/
- finality：https://academy.binance.com/en/glossary/finality
