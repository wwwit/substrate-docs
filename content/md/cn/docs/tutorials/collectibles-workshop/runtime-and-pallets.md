---
title: 模块构建器基础知识
description:
tutorial: 1
---

欢迎来到 Substrate 可收藏物品研讨会的第一部分。
这是一个交互式、实践性和自定进度的研讨会，介绍了使用[Substrate](https://substrate.io/developers/)构建基于区块链的应用程序的基本步骤。

在本研讨会中，您将了解基于 Substrate 的区块链的核心开发环境（运行时），以及插入运行时的模块库（称为模块）。

运行时是您为区块链定义特定于应用程序的逻辑的地方，因此本研讨会侧重于构建在区块链上运行的应用程序，而不是底层机制（例如点对点网络或共识），这些机制允许区块链中的计算机相互通信。

您在本研讨会中将构建的应用程序是一个区块链，它使用户能够创建和管理可收藏的数字资产。
由于这些资产将在区块链网络上进行管理，因此用户将能够转移和证明他们收集的资产的所有权。

注意：目前，只有当您使用 Substrate 节点模板的`branch = "polkadot-v1.0.0"`时，本研讨会才能编译。您可以使用`git checkout --detach polkadot-v1.0.0`命令签出此分支。