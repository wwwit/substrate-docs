---
title: 网络和节点
description: 描述基于 Substrate 的链的不同网络类型和节点角色。
keywords:
---

在考虑构建区块链时，将边界视为定义网络的要素非常有用。
例如，一组连接到单个路由器的计算机可以被视为家庭网络。
防火墙可能是定义企业网络的边界。
较小的隔离网络可以通过通用通信协议连接到广域网。
同样，您可以将区块链网络视为由其边界以及与其他区块链的隔离或通信来定义。

作为区块链构建者的工具包，Substrate 使您能够开发任何可以想象的区块链类型，并根据您的特定于应用程序的要求定义其边界。考虑到这种灵活性，您需要做出的决定之一是您要构建的网络类型以及不同节点在该网络中可能扮演的角色。

## 网络类型

基于 Substrate 的区块链可以在不同类型的网络架构中使用。
例如，Substrate 区块链用于构建以下网络类型：

- **私有网络**，限制对一组受限节点的访问。
- **独立链**，实现自己的安全协议，并且不连接或与任何其他链通信。
  比特币和以太坊是非 Substrate 基独立链的示例。
- **中继链**，为连接到它们的链提供去中心化的安全性和通信。
  Kusama 和 Polkadot 是中继链的示例。
- **平行链**，构建为连接到中继链，并且能够与使用相同中继链的其他链进行通信。
  由于平行链依赖于中继链来最终确定生成的区块，因此平行链必须实现与其目标中继链相同的共识协议。

## 节点类型

区块链需要网络节点同步，以呈现一致且最新的区块链状态视图。
每个同步节点都存储区块链的副本，并跟踪传入的交易。
但是，保留整个区块链的完整副本需要大量的存储和计算资源，并且对于大多数用例来说，从创世区块下载到最新区块的所有区块并不实用。
为了更容易维护链的安全性和完整性，但减少想要访问区块链数据的客户端的资源需求，存在不同类型的节点可以与链交互：

- [完整节点](#full-nodes)
- [存档节点](#archive-nodes)
- [轻客户端节点](#light-client-nodes)

### 完整节点

完整节点是区块链网络基础设施的关键部分，是最常见的节点类型。
完整节点存储区块链数据，并且通常参与常见的区块链操作，例如生成和验证区块、接收和验证交易以及响应用户请求提供数据。

![完整节点](/media/images/docs/full-node.png)

默认情况下，完整节点配置为仅存储最新的 256 个区块，并丢弃比该区块更旧的状态（创世区块除外），以防止完整节点无限增长并消耗所有可用磁盘空间。
您可以配置完整节点保留的区块数量。

虽然更旧的区块会被丢弃，但完整节点会保留从创世区块到最新区块的所有[区块头](/reference/glossary/#header)，以验证状态是否正确。
由于完整节点可以访问所有区块头，因此它可以通过从创世区块执行所有区块来重建整个区块链的状态。
因此，它需要更多的计算才能检索有关先前状态的信息，并且通常应使用存档节点。

完整节点允许您读取链的当前状态，并直接在网络上提交和验证交易。
通过丢弃来自更旧区块的状态，完整节点所需的磁盘空间远小于存档节点。
但是，完整节点需要更多的计算资源来查询和检索有关先前状态的信息。
如果您需要查询历史区块，则应清除完整节点，然后将其重新启动为存档节点。

### 存档节点

存档节点类似于完整节点，只是它们存储所有过去的区块，并且每个区块的完整状态都可用。
存档节点最常由需要访问历史信息的实用程序（例如区块浏览器、钱包、讨论论坛和类似应用程序）使用。

![存档节点](/media/images/docs/archive-node.png)

由于存档节点保留历史状态，因此它们需要大量的磁盘空间。
由于运行它们所需的磁盘空间，存档节点比完整节点更少见。
但是，存档节点使您能够方便地在任何时间点查询链的过去状态。
例如，您可以查询存档节点以查找特定区块中的账户余额，或查看导致特定状态更改的交易的详细信息。
当您在存档节点中的数据上运行这些类型的查询时，它们会更快、更高效。

### 轻客户端节点

轻客户端节点使您能够以最少的硬件要求连接到 Substrate 网络。

![轻客户端节点](/media/images/docs/light-node.png)

由于轻客户端节点所需的系统资源最少，因此它们可以嵌入到基于 Web 的应用程序、浏览器扩展、移动设备应用程序或物联网 (IoT) 设备中。
轻客户端节点提供运行时以及通过 RPC 端点访问当前状态。
轻客户端节点的 RPC 端点可以用 Rust、JavaScript 或其他语言编写，并用于读取区块头、提交交易以及查看交易的结果。

轻客户端节点不参与区块链或网络操作。
例如，轻客户端节点不负责区块生成或验证、交易闲聊或达成共识。
轻客户端节点不存储任何过去的区块，因此它无法在没有从拥有该数据的节点请求的情况下读取历史数据。

## 节点角色

根据您在启动节点时指定的命令行选项，节点可以在链的进展中扮演不同的角色，并且可以提供不同级别的对链上状态的访问权限。
例如，您可以限制有权生成新区块的节点以及哪些节点可以与对等节点通信。
未被授权为区块生成者的对等节点可以导入新区块、接收交易以及向其他节点发送和接收有关新交易的闲聊。
还可以阻止节点连接到更广泛的网络，并将其限制为与特定节点通信。

## 下一步去哪里

您可以使用 Substrate 构建几乎任何类型的网络，从完全独立的私有独立链到您自己的中继链生态系统或兼容的平行链。

要更深入地了解网络和节点类型，请探索以下主题。

- [构建本地区块链](/tutorials/build-a-blockchain/build-local-blockchain/)
- [模拟网络](/tutorials/build-a-blockchain/simulate-network/)
- [添加受信任节点](/tutorials/build-a-blockchain/add-trusted-nodes/)
- [授权特定节点](/tutorials/build-a-blockchain/authorize-specific-nodes/)