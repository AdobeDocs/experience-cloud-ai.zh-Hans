---
title: Experience Cloud 应用程序中的 AI
description: 了解 Experience Cloud 应用程序如何使用生成式 AI、AI 助手和代理式 AI。
source-git-commit: b5649a893afc212a826b1ec2acb5ee2957caa03d
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 3%

---

# Experience Cloud 中的 AI

欢迎阅读有关跨Adobe Experience Cloud应用程序的AI功能的综合指南。 本文档介绍了如何将创作AI、AI Assistant和Adobe代理集成到Experience Cloud工作流中，以提高工作效率并增强决策。

## 本指南包含的内容

### AI助手

[AI Assistant](./ai-assistant/ai-assistant-ui.md)是一种智能的对话式、创造性的AI工具，可在基于Adobe Experience Platform的应用程序中提高工作效率并重新定义工作。 用户可以通过自然语言提示获得产品知识、排除问题并找到操作见解。 您还可以使用AI Assistant访问Adobe Experience Platform代理和其他AI功能。

**主要功能：**

- **对话界面**：不同工作流首选项的全屏视图和边栏视图选项
- **发现提示**：按类别组织的预配置提示（学习、分析、优化）
- **上下文设置**：配置目标响应的应用程序、沙盒和数据视图设置
- **数据可视化**：用于数据见解的交互式图表和图形
- **响应验证**： Source引用、推理解释和反馈机制

### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md)是Adobe Experience Platform中的新代理层。 Experience Platform Agent Orchestrator旨在利用平台丰富的数据和客户知识，为专门构建的Adobe Experience Platform Agent专家提供智能和推理功能，使他们能够快速大规模地执行复杂的决策和问题解决任务，所有这些都由人为监督。 当您在像AI Assistant这样的对话界面中通过自然语言提出问题或请求帮助时，Agent Orchestrator会自动调用专业代理以获得正确的答案。 Agent Orchestrator会记住您的对话历史记录，使您能够自然地发展以前的问题，而无需重复上下文，并结合来自多个代理的洞察，为您提供清晰、统一的响应。

**核心组件：**

- **推理引擎**：创建逐步计划并根据需要调整方法
- **专用代理**：用于特定任务和域的专用代理
- **知识库**：安全访问业务智能和文档

### 专业代理

#### Audience Agent

提供有关受众的分析，包括：

- 检测受众规模的显着变化
- 识别重复受众
- 探索受众库存
- 检索受众大小

#### Data Insights Agent

此代理在Customer Journey Analytics中可用：

- 使用自然语言回答有关您的数据的问题
- 在Analysis Workspace中构建相关可视化图表
- 使用数据视图中的组件和实际数据

#### Journey Agent

使Journey Optimizer用户能够：

- 使用自然语言分析和优化历程
- 检测和解决计划或受众冲突
- 分析性能和流失点

#### 产品支持代理

提供自助调试和故障排除：

- 在不离开工作流的情况下对Adobe Experience Platform功能进行故障排除
- 通过AI助手交互的上下文创建支持工单
- 通过AI助手检查票证更新

## 快速入门

### 访问要求

要使用AI助手和Experience Platform代理，您的Adobe管理员需要设置适当的权限：

- **Real-Time CDP和Adobe Journey Optimizer**：操作问题需要“启用AI助手”权限和“查看操作分析”权限
- **Customer Journey Analytics**：通过Customer Journey Analytics访问控制访问产品知识和数据分析问题
- **Adobe Experience Manager**：通过Adobe Admin Console进行访问

### 隐私和安全性

AI Assistant构建时以隐私、安全和治理为重点：

- 培训不使用任何个人数据
- 所有现有的访问控制策略都有效
- 与Adobe Experience Platform Healthcare Shield一起使用时支持HIPAA
- 交互日志的30天保留策略
- 特定于沙盒的数据隔离

## 最佳实践

- 在提示中指定&#x200B;**以获取目标分析**
- **使用源引用和推理解释验证响应**
- **使用上下文设置**&#x200B;以确保相关数据源
- **提供反馈**&#x200B;以帮助提高AI助手性能
- **合并来自多个代理的见解**&#x200B;以进行综合分析

## 法律注意事项

- AI助手当前仅支持英语
- 始终验证响应，因为语言模型可能会出错
- 回顾推理步骤及解释
- 提交任何问题或不准确的反馈

本指南提供了在Experience Cloud应用程序中有效使用AI功能所需的一切，从基本交互到高级代理编排和专用工作流。
