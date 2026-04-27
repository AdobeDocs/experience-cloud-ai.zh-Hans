---
title: Experience Cloud 应用程序中的 AI
description: 了解 Experience Cloud 应用程序如何使用生成式 AI、AI 助手和代理式 AI。
TQID: https://experienceleague.adobe.com/heALjEZbowNaygG24oOM2HSlHa9oYVI5ViUNZDr19Ds
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 846
ht-degree: 17%

---

# Experience Cloud 中的 AI

欢迎阅读有关跨Adobe Experience Cloud应用程序的AI功能的综合指南。 本文档介绍了如何将创作AI、AI Assistant和Adobe代理集成到Experience Cloud工作流中，以提高工作效率并增强决策。

## 本指南包含的内容

### AI 助手

[AI Assistant](./ai-assistant/ai-assistant-ui.md)是一种智能的对话式、创造性的AI工具，可在基于Adobe Experience Platform的应用程序中提高工作效率并重新定义工作。 用户可以通过自然语言提示获得产品知识、排除问题并找到操作见解。 您还可以使用AI Assistant访问Adobe Experience Platform代理和其他AI功能。

**主要功能：**

- **对话界面**：您可以选择全屏界面和边栏视图界面，以符合您的工作流首选项。
- **发现提示**： AI Assistant提供预配置的提示，这些提示按“学习”、“分析”和“优化”等类别组织。
- **上下文设置**：您可以配置应用程序、沙盒和数据视图设置，以接收根据您的需求定制的响应。
- **数据可视化**：该工具提供交互式图表和图形，使您能够从数据中获取见解。
- **响应验证**：所有响应都包含源引用、AI推理解释以及提供反馈的机制。


### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md)是Adobe Experience Platform中的新代理层。 Experience Platform Agent Orchestrator 旨在利用平台的丰富数据和客户知识，为专门构建的专业 Adobe Experience Platform 代理赋予智能和推理功能，使后者在人为监督下大规模地快速执行复杂的决策和问题解决任务。 当您在 AI 助手这类对话界面中用自然语言提出问题或请求帮助时，Agent Orchestrator 会自动调用专门的代理来为您提供正确的回答。 Agent Orchestrator 会记住您的对话历史，使您能够自然地延续以前的问题，无需重复上下文，它还会结合来自多个代理的洞察，为您提供清晰、统一的回答。

**核心组件：**

- **推理引擎**：创建逐步计划并根据需要调整方法
- **专用代理**：用于特定任务和域的专用代理
- **知识库**：安全访问业务智能和文档

### 专业代理

#### Audience 代理

Audience Agent提供了有关受众的分析，包括：

- 检测受众规模的显着变化。
- 标识重复的受众。
- 探索受众库存。
- 检索受众大小。

有关详细信息，请阅读[Audience Agent文档](./agents/audience.md)。

#### Data Insights Agent

Customer Journey Analytics中的Data Insights Agent提供：

- 使用自然语言回答有关您的数据的问题。
- 在Analysis Workspace中构建相关可视化图表。
- 使用来自数据视图和实际数据的组件。

#### 历程分析代理

历程分析代理使Adobe Journey Optimizer用户能够：

- 使用自然语言分析和优化历程。
- 检测并解决计划或受众冲突。
- 分析性能和流失点。

有关详细信息，请阅读[Journey Agent文档](./agents/ajo-agent.md)。

#### 产品支持代理

使用产品支持代理进行自助调试和故障排除：

- 在不离开工作流的情况下对Adobe Experience Platform功能进行故障排除。
- 通过AI助手交互的上下文创建支持工单。
- 通过AI助手检查票证更新。

有关详细信息，请阅读[产品支持代理文档](./agents/product-support.md)。

<!--
#### Adobe Marketing Agent for [!DNL Microsoft 365 Copilot]

Use the Adobe Marketing Agent for [!DNL Microsoft 365 Copilot] to retrieve marketing insights from Experience Platform in [!DNL Microsoft 365] apps like [!DNL Teams], [!DNL Word], [!DNL Powerpoint], and [!DNL Excel]. With this agent, you can:

- Make faster, data-driven marketing decisions.
- Reduce time spent switching between tools.
- Simplify access to audience and journey insights across teams.

Read the [Adobe Marketing Agent documentation](./agents/ama-ms.md) for more information.
-->

## 快速入门

### 访问要求

要使用AI助手和Experience Platform代理，您的Adobe管理员需要设置适当的权限：

- 要在Real-Time CDP和Adobe Journey Optimizer中使用AI助手，您需要“启用AI助手”权限以及“查看操作分析”权限才能访问操作问题。
- Customer Journey Analytics中的AI助手通过Customer Journey Analytics访问控制进行管理，可让您询问产品知识和数据分析问题。
- 对于Adobe Experience Manager，您可以通过Adobe Admin Console中设置的权限访问AI助手。

### 隐私和安全性

AI Assistant构建时以隐私、安全和治理为重点：

- 培训不使用任何个人数据。
- 所有现有的访问控制策略都有效。
- 与Adobe Experience Platform Healthcare Shield一起使用时支持HIPAA。
- 交互日志的30天保留策略。
- 特定于沙盒的数据隔离。

## 最佳实践

要从AI Assistant体验中获取最大价值，请遵循以下最佳实践：

- 在提示中指定&#x200B;**&#x200B;**&#x200B;以从AI助手获取有针对性的相关见解。
- **通过查看源引用和AI助手提供的推理解释来验证响应**。
- **使用上下文设置**&#x200B;以确保您的问题使用了最相关的数据源。
- **提供反馈**&#x200B;以帮助随着时间的推移提高AI Assistant的性能和准确性。
- **合并来自多个代理的见解**，以获得更全面、更全面的分析。

## 法律注意事项

在使用AI助手时，务必要了解关键的法律和实际注意事项。 目前，AI Assistant仅支持英文回复。 务必小心验证提供的信息，因为语言模型偶尔会出错。 利用回答中包含的推理步骤和解释来更好地理解您收到的答案。 如果您遇到任何问题或不准确之处，请提交反馈以帮助逐渐改进AI助手。
