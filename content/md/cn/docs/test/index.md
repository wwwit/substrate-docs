---
title: 测试
description:
keywords:
---

无论您最终想要构建哪种类型的链，您都可能需要从本地开发环境开始进行单元测试和调试。
随着项目的进展，您需要在不同条件下评估不同操作的性能，以建立有关链中函数使用的执行时间和存储要求的基准。

如果您正在构建 Parachain，则在尝试部署到像 Rococo 这样的测试网络或像 Kusama 或 Polkadot 这样的实际生产网络（其中实际经济在起作用）之前，您还需要在本地网络中模拟一个或多个 Parachain 的操作。

在本地开发网络中，您可以完全控制您的节点。
您可以启动和停止节点。
您可以根据自己的判断修改、重新编译和升级运行时。
您可以根据需要写入和清除存储状态。
您可以使用预定义的帐户和 pallet 来尝试各种操作。
但是，测试是使您的链能够被更广泛的受众访问并在网络中具有经济可行性的关键。

本节中的主题重点介绍了测试区块链逻辑的工具和技术，以帮助您从本地开发过渡到在实际测试网络上部署，最终作为 Polkadot 生态系统的一部分投入生产。

- [单元测试](/test/unit-testing) 解释了如何使用 Rust 测试框架和模拟运行时环境来执行单元测试，这些测试可以验证代码的单个函数或模块。
- [调试](/test/debug) 描述了如何使用 Rust 日志记录函数来调试运行时。
- [基准测试](/test/benchmark) 解释了基准测试的作用，如何使用基准测试框架来评估代码中函数调用的性能，以及如何调整交易权重以准确反映执行时间。
- [模拟 Parachain](/test/simulate-parachains) 逐步介绍了如何设置本地测试网络以模拟具有验证者、Parachain collator 节点和 XCM 消息传递的中继链网络。
- [检查运行时](/test/check-runtime/) 解释了如何使用 `try-runtime` 命令行工具来测试运行时状态与链状态的生产快照。