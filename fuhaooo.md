---
timezone: Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# Alfred

之前在Web2从事Java开发工作，接触Web3后在积极参与相关社区活动，不断学习中。希望能够在残酷学习中坚持下来，顺利完成。

## Notes

<!-- Content_START -->

### 2024.12.10

### 1. Arbitrum 的使命

Arbitrum 的使命是通过提供更高效、低成本和用户友好的解决方案，增强以太坊生态系统的可扩展性和可用性。它致力于构建一个去中心化、高性能的 Layer 2 扩展平台，使开发者和用户能够享受更快、更便宜的交易，同时保持以太坊的安全性和去中心化特点。

### 2. Arbitrum 的特点

- 高扩展性
：Arbitrum 是以太坊的 Layer 2 扩展方案，可以显著提高交易处理能力，降低拥堵和交易费用。
- 与以太坊的兼容性
：完全兼容以太坊的 EVM（以太坊虚拟机），开发者可以无缝迁移现有智能合约和 DApp。
- 低成本
：利用 Rollup 技术，大幅降低了链上计算和存储成本，使得小额交易也具有经济性。
- 安全性
：继承以太坊主链的安全性，所有交易在 Layer 1 上的验证确保了去中心化和抗审查性。
- 灵活性
：支持多种开发工具和语言，例如 Solidity，同时为开发者提供良好的文档和社区支持。

### 2024.12.11

### 3. Arbitrum 的原理

Arbitrum 采用了 Optimistic Rollup 技术，通过将大量交易打包（Rollup）并发送到以太坊主链上记录和验证，实现扩展和成本降低。

#### 交易流程

- 用户提交交易：用户的交易首先被发送到 Arbitrum 的 Layer 2 网络。
- 批量打包：多个交易被打包成一个批次，并生成一个状态更新。
- 状态提交：批量交易的摘要（状态根）被提交到以太坊主链。
- 欺诈证明：如果有恶意操作，验证者可以提交欺诈证明，以挑战提交的状态并恢复正确性。

#### 核心技术

- Rollup 技术：将计算和存储移到链下，仅将交易摘要记录到主链。
- 欺诈证明机制：通过挑战者模型确保系统的正确性和抗审查性。
- 以太坊安全性继承：利用 Layer 1 的共识机制，保证 Arbitrum 的交易数据和状态更新的最终性。
### 2024.12.12

### 4. Rollup 概念概述
Rollup 是一种二层扩展解决方案，旨在提高区块链的可扩展性和性能，特别是在以太坊等区块链上。通过将大量交易和计算工作“卷起”并批量处理，这些交易的执行和数据存储仍然依赖于主链（如以太坊），但通过将交易的计算和存储从主链转移到二层，显著提高了交易吞吐量和降低了费用。

原理：
- 成本优化：将⼤部分运算与存储任务移交至L1链下也即L2上。
- 安全保障：L2上的交易内容与交易后的状态，会同步⾄以太坊L1，通过合约来校验 状态转换的有效性。

Rollup 的核心概念是将交易数据打包到主链之外进行处理，但通过机制保证数据的完整性和安全性。这使得它可以提供和主链一样高的安全性，同时大幅提高处理速度和降低成本。常见的 Rollup 类型包括 Optimistic Rollups 和 ZK-Rollups

> 非交互型 rollup（如，ZK-Rollup）、单轮交互型 rollup（如 “optimistic rollup” 提案）和多轮交互型 rollup （如 Arbitrum Rollup ）

防止Rollup排序器作恶的状态校验⽅式，分为欺诈证明（Fraud Proof）和有效性证明（Validity Proof）两类。使⽤欺诈证明的Rollup⽅案称为OP Rollup（Optimistic Rollup，OPR），⽽因为一些历史包袱，使⽤有效性证明的Rollup往往被称为ZK Rollup（Zero-knowledge Proof Rollup，ZKR)，而不是Validity Rollup。

### 5. Fraud Proofs 欺诈证明机制
欺诈证明机制 是在 Optimistic Rollups 中用来确保二层链正确性的机制之一。在这种模型下，交易的执行被假定是有效的，直到有人提出异议（即“挑战”）。这种机制可以通过以下步骤工作：

- 交易提交：用户在二层 Rollup 上发起交易，交易数据和状态变更会被“卷起”并提交到以太坊主链。主链会记录这些批量交易的哈希值。

- 乐观执行：在 Optimistic Rollup 中，假设这些交易是有效的，并且会在链上验证这些交易。理论上，交易会立即被认为是有效的，不需要立即进行复杂的计算。

- 欺诈挑战期：将状态提交到 Rollups 合约后，有一个时间窗口允许其他参与者查看这些交易。如果某个参与者认为 Rollup 上的某个交易是不合法的或恶意的，他们可以提出一个 欺诈证明，即对该交易的合法性进行挑战。

- 欺诈证明的验证：当有人提出欺诈证明时，网络会进行审查，验证该交易是否真正无效。如果证明成功，恶意或无效的交易会被回滚，相关提交的交易也会被撤销。

- 奖励和惩罚：提出有效欺诈证明的挑战者会获得奖励，而那些提交无效交易的节点（比如欺诈者）则会受到惩罚。惩罚通常是扣除抵押金，或者其他形式的经济惩罚。

### 2024.12.13
### 6. Zero-Knowledge Proof 零知识证明机制
零知识证明（简称 ZKP）是一种密码学方法，允许一方（证明者）向另一方（验证者）证明某个声明是真实的，而无需透露任何与该声明相关的具体信息。自20世纪80年代首次提出以来，零知识证明在隐私保护、身份验证、区块链技术等多个领域得到了广泛应用和深入研究。

零知识证明是一种协议，满足以下三个核心属性：
- 完备性（Completeness）：如果声明为真，诚实的验证者将在协议结束时被说服。
- 可靠性（Soundness）：如果声明为假，恶意的证明者无法说服诚实的验证者，除非以极低的概率。
- 零知识性（Zero-Knowledge）：如果声明为真，验证者不会学到任何除了声明为真之外的其他信息。

### 7、Rollup 协议
欺诈证明虽然不能像零知识证明那样具有⾼度的简洁性，但Arbitrum使⽤了⼀种“多轮分割-单步证明”的轮流式交互流程，最终需要证明的仅仅是单⼀的虚拟机操作码，成本相对较⼩。

Rollup协议的核心合约是RollupProxy.sol，在保证数据结构一致的情况下，使用了一个罕见的双重代理结构，一个代理对应两个实现RollupUserLogic.sol和RollupAdminLogic.sol，在Scan等工具中目前还无法很好的解析。

另外还有ChallengeManager.sol合约负责管理挑战，OneStepProver系列合约来判定欺诈证明。
![image](https://github.com/user-attachments/assets/a021e2c0-a0df-4125-912c-0fc22d246028)

ChallengeManager合约负责验证对挑战步骤的细分过程：

1.细分是一个双方轮流互动的过程，一方对某个Rollup Block中包含的历史数据进行分段，另一方指出是哪部分数据片段有问题。类似于二分法（实际是N/K）不断渐进缩小范围的一个过程。

2.之后，可以继续定位至哪条交易及结果有问题，再进一步细分至该交易中有争议的某条机器指令。

3.ChallengeManager合约只检查对原始数据进行细分后，产生的『数据片段』是否有效。

4.当挑战者和被挑战者定位到了将被挑战的那条机器指令后，挑战者调用oneStepProveExecution()，发送单步欺诈证明，证明这条机器指令的执行结果有问题。

### 8、单步证明
单步证明是整个Arbitrum的欺诈证明的核心。WAVM，Wasm Arbitrum Virtual Machine，它是一个由ArbOS模块和Geth（以太坊客户端）核心模块共同编译成的虚拟机。由于L2与L1有许多截然不同的地方，原始的Geth核心必须经过轻量修改，并且配合ArbOS一起工作。所以，L2上的状态转换其实是ArbOS+Geth Core的共同手笔。
![image](https://github.com/user-attachments/assets/095379f9-7565-4401-bf78-0be0a7d38d71)

Arbitrum的节点客户端（排序器、验证者、全节点等），是将上述ArbOS+Geth Core处理的程序，编译为节点主机能直接处理的原生机器代码（for x86/ARM/PC/Mac/etc.）。

如果把编译后得到的目标语言更改为Wasm，就得到了验证者生成欺诈证明时使用的WAVM，而验证单步证明的合约上，模拟的也是WAVM虚拟机的功能。

那为什么在生成欺诈证明时，要编译为Wasm字节码？主要还是因为，验证单步欺诈证明的合约，要用以太坊智能合约模拟出 能处理某套指令集的虚拟机VM，而WASM易于在合约上实现模拟。
![image](https://github.com/user-attachments/assets/149c286b-e139-46e5-b715-9c81820c68a7)

但WASM相比于Native机器代码，运行速度略慢，所以只有在欺诈证明生成及验证的时候，Arbitrum的节点/合约才会用到WAVM。

在之前的多轮互动细分后，单步证明最终证明的是WAVM指令集中的单步指令。

### 2024.12.14

### 9、Retryables 可重试票据
跨链都是异步和非原子性的，它不可能像在一条链上一样做完一笔交易确认后就知道结果，也不能保证另一侧一定会在某个时间点发生某些事。因此跨链有可能因为一些软性问题而失败，但只要使用正确的手段，诸如可重试票据（Retryable Ticket），就不会发生资金卡住等硬性问题。

可重试票据是通过Arbitrum官方桥充值时，用到的基本工具，ETH和ERC20的充值都会使⽤到。其⽣命周期分为三步：

1. 在L1上提交票据。在Delayed Inbox合约中使用createRetryableTicket()方法创建充值票据，并提交。

2. L2上自动兑付。大部分情况下，排序器可以自动帮用户兑付票据，无需后续的手动操作。

3. L2上手动兑付。部分边缘情况，如L2上gas价格突然激增，票据上预付的gas不够，则无法自动兑付。此时需要用户手动操作。

注意，如果自动兑付失败，需要在7日内手动兑付票据，否则要么票据将会被删除（资金会永久损失），要么需要为票据的保存支付一定费用来续租。

另外，对于Arbitrum官方桥的提现流程，虽然和充值行为在流程上有一定对称相似性，但并没有Retryables这个概念，一方面可以从Rollup协议本身理解，另一方面我们可以从一些区别进行理解：

1. 提现的过程中不存在自动兑付，因为EVM没有定时器或自动化，而L2上可以实现自动兑付，是排序器帮忙实现的，所以L1上用户要手动与Outbox合约交互，以Claim取回资产。

2. 提现也不存在票据过期的问题，只要过了挑战期，可以在任意时间领取。

### 10、ERC-20资产跨链 Gateway
![image](https://github.com/user-attachments/assets/b519b20f-4e82-4f6f-8093-0a6aa1eb52d1)
Arbitrum使用了Gateway系统，解决了大部分ERC20跨链的痛点，具有以下特性：

Gateway组件在L1和L2成对出现。

Gateway Router负责维护Token L1Token L2之间的地址映射，以及some tokensome gateway之间的映射。

Gateway本身可分为StandardERC20 gateway，Generic-custom gateway，Custom gateway等等，用以解决不同类型的和功能ERC20的桥接问题。

我们以比较简单的WETH跨链为例，来说明自定义gateway的必要性。

WETH是一种ETH的ERC20等价物。Ether作为主币，很多dApp中的复杂功能是无法实现的，因此需要一个ERC20的等价物。向WETH合约内转入一些ETH，它们会被锁在合约内，并生成出相同数量的WETH。

同理，也可以销毁WETH，取出ETH。显然，流通的WETH和锁仓的ETH数量永远是1：1的。

如果现在把WETH直接跨链到L2上，我们会发现一些奇怪的问题：

无法在L2上把WETH进行Unwrap变成ETH，因为L2上并没有锁仓对应的ETH。

Wrap功能可以使用，但这些新生成的WETH如果跨回到L1，也无法在L1上解封装为ETH，因为L1和L2上的WETH合约不是“对称的”。

显然这违反了WETH的设计原理。那么WETH在跨链时，不论是充值还是提现，都需要先Unwrap成ETH后，再跨到对面，然后Wrap成WETH。这个也就是WETH Gateway的作用。

其他有更复杂逻辑的代币同理，需要更复杂和精心设计的Gateway才能正常在跨链环境下工作。Arbitrum的自定义Gateway继承了普通Gateway的跨链通信逻辑，并允许开发者自定义与代币逻辑相关的跨链行为，可满足大部分需求。

### 11、Delayed Inbox 慢收件箱
与快箱也即 SequencerInbox相对应的是慢箱 Inbox （全称Delayed Inbox）。为什么要有快慢之分呢？因为快箱是专⻔接收排序器发布的L2交易Batch的，所有未经排序器在L2网络内预处理的交易，都不该出现在快箱合约中。

慢箱的第⼀点作⽤是，处理L1到L2的充值⾏为。⽤户通过慢箱进⾏充值，排序器监听到后再反映在L2上，最终这笔充值记录会被排序器包含进L2的交易序列中，并提交⾄快箱合约Sequencer Inbox。

在这个例⼦中，⽤户直接向快箱提交充值交易是不合适的，因为提交到快箱Sequencer Inbox中的交易，会干扰到Layer2正常的交易排序，然后会影响到排序器的工作。

慢箱的第⼆个作⽤，是抗审查。用户直接提交⾄慢箱合约中的交易，排序器⼀般会在10分钟内归集到快箱中。但如果排序器恶意忽略你的请求，慢箱还有⼀个强制归集force inclusion功能：

如果交易被提交至Delayed Inbox中，经过24小时，慢箱中的交易仍未被排序器包含至交易序列中，用户可以在Layer1上手动触发force inclusion函数，把被排序器忽略掉的交易请求，强制归集到快箱Sequencer Inbox中，之后就会被全体Arbitrum One节点监听到，会被强制包含进Layer2交易序列里。

我们刚才提到过，快箱⾥的数据就是L2的历史数据实体。所以在被恶意审查的情况下，通过慢箱可以让交易指令最终包含进L2账本中，这涵盖了强制提款等逃离Layer2的场景。

由此可以看出，对任何⼀个⽅向和层次的交易，排序器最终都⽆法永久审查你。

### 12、Outbox 出站箱
出站箱Outbox只与提现有关，可以理解为提现行为的记录和管理系统：

我们知道，Arbitrum官方桥的提现需要等待约7天的挑战期结束， Rollup Block 最终敲定后，提款行为才可以实施。⽤户在挑战期结束后，向Layer1上的Outbox合约提交相应的Merkle Proof，它再与其他职能的合约通信（如解锁其他合约中锁定的资产），最终完成提现。

OutBox合约会记录哪些L2到L1的跨链消息已经被处理过，以防止有人反复提交执行过的提现请求。它通过mapping(uint256 => bytes32) public spent，记录提现请求的spent Index与信息对应关系，如果mapping[spentIndex] != bytes32(0)则该请求已被提现过。原理类似于防止重放攻击的交易计数器Nonce。

### 2024.12.15

### 充值与提现流程

以ETH为例完整讲解充值与提现的流程。ERC20与之不同的仅仅是⾛了Gateway

### ETH充值
![image](https://github.com/user-attachments/assets/a7fa9e0f-001b-43c8-a12e-d3338d86f4a0)

1. 用户调用慢箱的depositETH()函数。

2. 该函数会继续调用bridge.enqueueDelayedMessage()，在bridge合约中记录该消息，并将ETH发送往bridge合约。所有的ETH充值资金，都保管在bridge合约中，相当于一个充值地址。

3. 排序器监听到慢箱中的充值消息，将充值操作反映⾄L2数据库中，⽤户可以在L2网络看到自己充进来的资产。

4. 排序器将该笔充值记录包含进交易批次batch，提交给L1上的快箱合约。

### ETH提现
![image](https://github.com/user-attachments/assets/3da94536-68f7-429d-bf36-acded86fe2e8)

1. ⽤户在L2上调⽤ ArbSys合约的withdrawEth()函数 ，在L2上销毁相应数量的ETH。

2. 排序器将该提现请求发送⾄快箱。

3. Validator节点根据快箱中的交易序列，创建新的Rollup Block，其中会包含上述提款交易。

4. Rollup Block度过了挑战期并被确认后，⽤户可以在L1上调用Outbox.execute Transaction()函数，证明参数由前面提到的ArbSys合约给出。

5. Outbox 合约确认⽆误后，解锁bridge中相应数额的ETH发送给⽤户。

### 强制提现
force Inclusion()强制归集功能用于对抗定序器的审查，任何L2本地交易、L1到L2交易和L2到L1交易，都可以使用该功能实现。定序器的恶意审查严重影响了交易体验，大部分情况下我们会选择提现离开L2，因此下面以强制提现为例介绍forceInclusion的用法。

回顾在ETH提现步骤中，只有步骤1、2是涉及到定序器审查的，所以只需要更改这两步：

调用L1上慢箱合约中的inbox.sendL2Message()，输入参数就是在L2上调用withdrawEth()时需要输入的参数。该消息会共享给L1上的bridge合约。

等待24小时的强制归集等待期后，调用快箱中的force Inclusion()进行强制归集，快箱合约会检视bridge中是否有对应消息。

最终用户可以在Outbox中提现，其余步骤由同正常的提现相同。

另外，arbitrum-tutorials中也有使用Arb SDK的详细教程去指导用户如何通过forceInclusion()去进行L2本地交易和L2到L1交易。

### 2024.12.16

### Arbitum One 架构
![image](https://github.com/user-attachments/assets/f49fdd66-b14a-4bdc-8b14-6b79af87efc0)
- Arbitrum 的架构有部分在 L1 上，有部分在 L2 上。在 L1 上的组件是 EthBridge，由一组以太坊合约构成。EthBridge 负责对 Arbitrum Rollup 协议进行仲裁，以及维护 Arbitrum rollup 在以太坊链上的收件箱和发件箱。
- 用户、L1 合约和全节点可以通过以太坊链上的收件箱和发件箱将其交易发送至 Arbitrum 链，并观察这些交易的结果。
- Arbitrum 虚拟机（AVM）是 EthBridge 提供的功能，是 L1 和 L2 之间的网关。AVM 能够读取输入，并基于这些输入执行计算，从而产生输出。
- ArbOS 运行在 AVM 上，确保智能合约在 Arbitrum 链上执行。ArbOS 完全存在于 L2 上，并像在以太坊上一样运行 EVM 合约。

### Arbitrum Classic 多轮交互式欺诈证明
Arbitrum 采用多轮欺诈证明。简单来说，就是通过二分查找，找到引起分歧的那个区块的第一个操作码。找到之后，只需在链上执行这个操作码。纠纷解决协议的结果是一个参与者将被发现是错误的。这个参与者的押金会被罚没。押注会从所在的方框上删除。部分押金会给到纠纷的另一方，剩下的被烧掉。

- 当两个质押者押注不同的区块且这两个区块之间没有继承关系时，他们会在某个区块上产生分歧，从而引发挑战。
- 挑战主要发生在 Arbitrum 链上，由 L1 合约裁决。
- 挑战包括一个在 L2 上进行的交互型多轮切分游戏和一个在 L1 上执行的单步证明。
- 如果有质押者对某个区块提出争议，提议该区块的质押者将作为 “被告” 捍卫自己的断言。在切分游戏中，作为 “被告” 的质押者（Alice）为先手，将 N 个指令切分成 K 段，每段的大小是 N/K，且每段都有一个起点和一个终点。
- 作为 “原告” 的质押者（Bob）同样将 N 个指令切分成 K 段（每段的大小是 N/K），并将它们与 Alice 的切分段一一对应，发现其中一个切分段的终点与 Alice 的不同。
  - Bob 实际上是在找出他不认同的切分段。
- 接着，Bob 会执行 Alice 最初的操作，将有争议的切分段（大小为 N/K）再切分成 K 个子段，然后将这个切分段连同子段一起发送给 Alice。Alice 执行 Bob 最初的操作，找到终点不同的那个子段。
- 切分流程继续下去，直到 Alice 和 Bob 找到他们产生分歧的那一个指令为止。这个指令被发送给 L1 合约，并由后者执行它，然后决定这场争议的 “胜诉方”。
- “败诉方” 将失去质押物，一部分质押物将被销毁（防止攻击者对冲押注），其余则奖励给诚实的 “胜诉方”。
- 在整个切分流程中，作为裁决方的 L1 合约不知道任何关于指令的信息，只负责核实双方是否遵循游戏规则。
- 在争议期间，其他所有验证者都能在争议敲定之前自行断定争议的结果，这就意味着会发生软分叉，且验证者可以继续在正确的链上提交 Rollup 区块。
- 挑战期有一个强制的期限，即，每个质押者大约一周时间。
- 每个质押者必须在一周的限期内完成自己的任务，否则就会 “败诉”。
- 多个纠纷可以同时解决，但是每个押注者一次最多只能参与一个纠纷。

### Arbitrum Nitro
2022 年 8 月，Arbitrum One 网络升级为 Arbitrum Nitro。Nitro 使用 WebAssembly（WASM）架构将取代原先的 Arbitrum EVM（AVM）架构，其新的证明器（prover）可以在 WASM 代码上进行 Arbitrum 的交互式欺诈证明。此外，Gethcore 也直接编译到 Arbitrum 中，使其更兼容 EVM。
> 为什么升级：https://docs.arbitrum.io/how-arbitrum-works/why-nitro （更低的费用、更好的以太坊兼容性和简单性）

Nitro 的精髓及其关键创新在于四大理念：

- 排序，然后是确定性执行：Nitro 采用两阶段策略处理交易。首先，将交易组织成一个有序序列，然后 Nitro 按照该序列提交。然后，按照该序列通过确定性状态转换函数处理交易。

- Geth 为核心：Nitro 通过编译流行的 go-ethereum（“Geth”）以太坊节点软件的核心代码来支持以太坊的数据结构、格式和虚拟机。以这种方式使用 Geth 作为库可确保与以太坊的高度兼容性。

- 将执行与证明分开：Nitro 采用相同的源代码并将其编译两次，一次编译为本机代码以便在 Nitro 节点中执行，以优化速度，再次编译为 WASM 用于证明，以优化可移植性和安全性。

- 具有交互式欺诈证明的乐观汇总：Nitro 使用乐观汇总协议将交易结算到第 1 层以太坊链，其中包括 Arbitrum 开创的交互式欺诈证明。

#### 排序，然后确定性执行
![Nitro 中交易的处理方式](https://github.com/user-attachments/assets/dc4fd517-f206-4a9f-b4bb-465dca521e30)
首先，用户创建交易，使用钱包对其进行签名，然后将其发送到 Nitro 链的 Sequencer。顾名思义，排序器的工作是获取到达的事务，将它们放入有序序列中，然后发布该序列。

一旦事务被排序，它们就会按顺序通过状态转换函数一一运行。状态转换函数将链的当前状态（账户余额、合约代码等）以及下一笔交易作为输入。它会更新状态，有时会在 Nitro 链上发出新的第 2 层区块。

因为协议不信任定序器不会将垃圾放入其序列中，所以状态转换函数将检测并丢弃序列中的任何无效（例如，格式不正确）事务。一个表现良好的 Sequencer 会过滤掉无效的交易，这样状态转换函数就永远不会看到它们——这降低了成本，从而使交易费用保持在较低水平——但无论 Sequencer 在其 feed 中放入什么内容，Nitro 仍然可以正常工作。 （提要中的交易由其发送者签名，因此排序器无法创建伪造的交易。）

状态转换函数是确定性的，这意味着它的行为仅取决于当前状态和下一个事务的内容，而不依赖于其他任何东西。由于这种确定性，交易 T 的结果将仅取决于链的创世状态、序列中 T 之前的交易以及 T 本身。

由此可见，任何知道交易序列的人都可以自己计算状态转换函数，并且所有这样做的诚实方都保证得到相同的结果。这是 Nitro 节点操作的正常方式：获取交易序列，并在本地运行状态转换函数。为此不需要共识机制。
<!-- Content_END -->
