---
title: 贡献者指南
description:
keywords:
  - 贡献
  - 风格指南
---

感谢您对 Substrate 开发框架文档贡献的兴趣。
作为社区的一员，我们邀请并鼓励您为不断发展的技术文档和代码库做出贡献。
有很多方法可以参与其中。
例如，您可以通过以下方式做出贡献：

- 提交问题
- 为现有内容提供改进建议
- 为现有的拉取请求添加审查评论
- 提出新内容
- 创建新的拉取请求以自行修复问题
- 为其他社区成员可能觉得有用的新内容创建拉取请求

我们重视、尊重和感谢开发者社区的所有贡献，并且只要求您同意遵守我们的 [行为准则](https://github.com/paritytech/substrate/blob/master/docs/CODE_OF_CONDUCT.md) 并遵循这些贡献者指南。

要了解有关如何贡献的更多信息，请参阅以下主题：

- [在您贡献之前](#before-you-contribute)
- [如何贡献](#how-to-contribute)
- [贡献什么](#what-to-contribute)

## 在您贡献之前

在贡献之前，请花几分钟时间查看这些贡献者指南。
贡献者指南旨在使贡献过程对参与解决您的问题、评估更改和完成您的拉取请求的所有人员都变得简单有效。

在贡献之前，请考虑以下事项：

- 如果您想报告问题，请单击 **问题** 并提供尽可能多的有关问题的信息。

- 如果您有技术问题或需要帮助查找特定信息，请在 [Stack Exchange](https://substrate.stackexchange.com/) 上发布您的问题。

如果您想直接为此存储库做出贡献，典型的修复可能包括以下任何一项：

- 拼写、语法或错别字修复。
- 代码缩进、空格或格式更改。
- 损坏或丢失的链接。

请注意，对该存储库的任何贡献都必须以 **拉取请求** 的形式提交。
在创建拉取请求之前，请确保拉取请求仅实现一个错误修复。

如果您不熟悉使用 GitHub 存储库和创建拉取请求，请考虑探索 [First Contributions](https://github.com/firstcontributions/first-contributions) 或 [如何在 GitHub 上为开源项目做出贡献](https://egghead.io/courses/how-to-contribute-to-an-open-source-project-on-github)。

## 如何贡献

此存储库包含 [docs.substrate.io](https://docs.substrate.io) 站点的文档源代码，主要侧重于 Substrate 区块链开发者和平行链开发者的文档。

### 进行简单的编辑

对于简单的更改，例如更正错别字或对句子进行细微更改：

1. 单击 **编辑此页面**。

2. 在 GitHub 中编辑页面。

3. 将默认提交消息替换为您更改的简短描述，然后单击 **提交更改**。

4. 选择 **为此提交创建新分支并启动拉取请求**。

### 创建分支和拉取请求

如果您的贡献不仅仅是简单的更改，则需要遵循创建工作分支和提交拉取请求的完整工作流程。
以下是您需要执行的操作摘要：

1. 在 Web 浏览器中导航到 [substrate-docs](https://github.com/substrate-developer-hub/substrate-docs) 公共存储库。

2. 克隆或派生存储库以在本地计算机上创建存储库的副本。

3. 通过运行类似于以下内容的命令为您的修复创建新分支：

   ```text
   git switch -c my-initials/my-branch-name-here
   ```

4. 在文本编辑器中打开要修复的文件，并对要解决的问题进行相应的更改。

5. 通过运行类似于以下内容的命令添加已更改文件的文件内容：

   ```text
   git add path-to-changed-file
   ```

6. 通过运行类似于以下内容的命令将更改提交到存储库，并附带描述性消息：

   ```text
   git commit -m "Description of the fix being committed."
   ```

7. 通过运行类似于以下内容的命令将更改推送到远程存储库：

   ```text
   git push origin my-initials/my-branch-name-here
   ```

8. 单击 **创建拉取请求** 以启动新的拉取请求，并提供有关您所做更改的任何其他信息。

   维护人员将审查您的拉取请求并批准或请求更改。
   如果不需要更改，维护人员将合并您的拉取请求。
   如果维护人员请求更改或澄清，请更新您的拉取请求并请求另一位审阅者。

9. 当您看到您的更改已合并时，庆祝您的成功！
   🥂

## 贡献什么

社区最有价值的贡献通常以操作指南或教程的形式出现，这些指南可以帮助其他开发者解决特定问题、学习特定技能或演示特定任务。

如果您想做出贡献，您可能想知道“‘操作指南’和教程有什么区别？”。

### 操作指南

操作指南描述了如何实现目标或完成任务。
仅包含与实现该目标或完成任务相关的必要信息。
借助操作指南，读者有足够的信息来了解他们想做什么——例如，开立银行账户——但不一定有足够的信息来了解如何去做。
例如，开立银行账户的操作指南不会解释什么是银行账户或为什么要开立银行账户，而是会重点介绍以下具体步骤：

1. 选择一家机构。
2. 填写申请表。
3. 存入最低金额的货币。

操作指南通常包含指向其他信息的链接，但不应包含会分散读者想要完成的目标的解释。
有关撰写 _操作指南_ 的更多信息，请参阅 [模板 - 操作指南](/community/template-how-to-guide) 和 [Markdown 模板](https://github.com/substrate-developer-hub/substrate-docs/blob/main/static/assets/contribute-templates/how-to-template.md)。

### 教程

教程是一个动手演示或课程，使读者能够获得
**高度可预测** 的结果。
教程假设读者对所涵盖的主题没有任何先验知识，并且他们需要明确的指导才能完成每个步骤以达到 **众所周知** 的结果。
通常，教程是一个引导式游览，帮助读者从头到尾完成一项完整的任务。
没有绕路，信息也不应分解成子主题，因为必须按顺序完成步骤，而不是按照读者选择的顺序。

教程中最重要的一个方面是，它始终应产生成功且预期的结果。
成功的成果是激发读者信心和喜悦的原因。
操作指南和教程之间最重要的区别在于，在教程中，作者决定目标是什么，并且作者消除了所有会分散对目标成功实现的注意力。

<!--
### 撰写操作指南的建议

Substrate 开发者中心旨在为 Substrate 开发者社区和更广泛的生态系统提供模块化且可扩展的资源框架。
为了实现这一目标，我们希望使贡献者能够轻松地集成遵循一些指导原则和结构和样式的基本约定的新内容。
作为内容创建者，您应该牢记以下一般原则：

- ◼️ 模块化。每个指南都有明确的重点。
  但是，如果信息在一个以上指南中都有用，您可以将其抽象成一个独立的主题并在多个地方重复使用。

- 🔗 链接。指南应在有用的地方使用链接——例如，引导读者了解
  概念或参考主题——但请注意，失效的链接会让读者感到沮丧。

- ⏯️ 示例。有用的代码示例是创建有用指南的关键组成部分。

- 🛰️ 相关参考。指南可以包含指向相关资源的链接，例如 Rust 文档、视频内容或其他指南和教程。

### 操作指南的类别

操作指南被分组到不同的类别中，以帮助对其进行组织。
源文件使用标签来识别适用的类别以及每个指南的复杂程度。
作为内容贡献者，您还可以使用标签来识别复杂程度以及内容最合适的类别。
当前的分组反映了 Substrate 中的不同开发领域：

- 基础知识。真正简单的指南所在的位置，这些指南可以被更复杂的指南引用。

- 模块设计。与使用或不使用 FRAME 构建自定义模块有关的一切。

- 权重。涵盖为特定用例配置权重的任何内容。

- 测试。测试指南的集合。

- 存储迁移。与存储迁移有关的一切。

- 共识。点对点网络、不同的共识模型、桥接、节点配置。

* 平行链。与构建平行链功能相关的指南。

### 复杂度

从以下列表中添加最合适的标签来指定复杂度级别：

- beginner
- intermediate
- advanced

#### 信息类别

从以下列表中添加最合适的标签来指定文章的类别：

- basics
- client
- consensus
- currency
- fees
- frame-v1
- migration
- node
- pallet design
- proof-of-work
- runtime
- storage
- testing
- weights
- parachains
- contracts
-->