---
title: Experimentation Agent
description: Learn how to use Experimentation Agent
TQID: https://experienceleague.adobe.com/ARh16ylmUDrp---g8KuYNyewIv54IQ53pxoE2g700o0
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bcc5edb5-84c3-4940-9f84-ed88b6c16274
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 555
ht-degree: 4%

---

# Experimentation Agent

>[!AVAILABILITY]
>
>The Experimentation Agent is available to all customers who have purchased the paid license of Journey Optimizer Experimentation Accelerator and integrates seamlessly with either Adobe Target or Adobe Journey Optimizer.
>
>[Learn more on Journey Optimizer Experimentation Accelerator](https://experienceleague.adobe.com/zh-hans/docs/experimentation-accelerator/using/overview)

## 概述

The **Experimentation Agent** is an AI-powered tool that modernizes how you can run and manage digital experiments across websites, emails, push messages, and applications. Built on Adobe Experience Platform AI platform and experimentation tools, the **Experimentation Agent** helps you run experiments more efficiently, organize business goals, and generate actionable insights, highlighting what worked, what did not, and where to experiment next.

The following permissions in order to fully use the Experimentation Agent features.

* **View Experiments**: This permission lets you use the Experimentation Agent to view insights into the experiment directly in AI Assistant.

* **Manage Experiment Metada**: This permission lets you use the Experimentation Agent to create new experiments directly in AI Assistant.

➡️ [Learn more in Journey Optimizer Experimentation Accelerator documentation](https://experienceleague.adobe.com/zh-hans/docs/experimentation-accelerator/using/get-started/experiment-accelerator-access)

As part of Experimentation Accelerator feature, the Agent delivers:

* **Performance**: a clear view of what happened in the experiment

* **Insights**: an explanation of why the results occurred

* **Opportunities**: guidance on the next actions to take

![Sample for Experimentation Agent](./images/experiment/experiment-agent.png)

## 用例

The Experimentation Agent enhances each phase of the experimentation workflow by analyzing results, interpreting content, and suggesting next steps.

Its capabilities can be grouped into five key functions:

* **Experiment Summarization**

  Provide a clear, non-technical overview of experiment results for stakeholders.

* **Content Analysis**

  Examine the messaging or creative elements of treatments to understand why certain ones outperformed others.

* **Attribute Identification**

  Categorize treatments by their key attributes, e.g., themes, tones, formats, and connect those attributes to conversion outcomes.

* **推荐生成**

  根据先前实验的见解，建议新的治疗方法或测试调整。

* **个机会**

  确定更广泛的领域或新的实验角度，以发掘未开发的潜力。

## 范围和范围外功能

### **范围内**

当前支持以下功能：

* 性能
* Insights
* 机会

### **范围外**

目前不支持以下功能：

* 创建或编辑试验
* 使用多个量度报告用例

## 示例提示

以下是一组提示示例，可帮助您开始使用Experimentation Agent：

### 一般问题

| 提示 |
|-|
| 正在运行哪些试验？ |
| `<campaign name>`正在运行哪些试验？ |
| 上个月开始了哪些实验？ |
| 过去一年中有多少实验结束？ |
| 哪些实验当前已暂停/停止/等？ |
| 从最近的测试中出现了哪些常见模式？ |
| 上季度实验的平均持续时间是多少？ |

### 性能问题

| 提示 |
|-|
| 对于我的`<experiment name>`，采用哪种处理方式？ |
| `<experiment name>`的提升度是多少？ |
| 哪些实验具有统计学意义的结果？ |
| 哪些实验的转化率最高？ |

### 分析问题

| 提示 |
|-|
| 什么是`<experiment name>`测试？ ? |
| 我们从`<experiment name>`中学到了什么？ |
| 你能告诉我为什么治疗一个韩元吗？ |
| 入选变体中的趋势是什么？ |
| 从最近的测试中出现了哪些常见模式？ |
| `<experiment name>`中发生了任何意外情况吗？ |

### 机会问题

| 提示 |
|-|
| 你建议我在这个实验之后做什么？ |
| 是否有任何改善`<experiment name>`的方法？ |
| `<experiment name>`之后哪些机会变得更清晰？ |
| 接下来我可以测试哪些内容来证明`<experiment name>`的假设验证？ |
| 我应该实施哪些其他用例？ |
