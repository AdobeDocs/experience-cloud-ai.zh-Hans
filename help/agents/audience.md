---
title: Audience Agent
description: 了解如何使用Audience Agent创建受众、查看受众更改、检测重复的受众以及查看受众分析。
source-git-commit: d91aac948a6fef36949218004dc0481dc8f5cf7f
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---


# Audience Agent

>[!AVAILABILITY]
>
>Audience Agent适用于有权访问AI Assistant的所有客户。 但是，您需要以下权限才能完全使用Audience Agent功能。
>
>**查看区段**：此权限允许您使用Audience Agent直接在AI助手中查看受众分析。
>>**管理区段**：“收件人”权限允许您使用Audience Agent直接在AI Assistant中创建新受众。

通过Audience Agent，您可以查看有关受众的分析，包括检测受众规模的显着变化、检测重复的受众、探索受众资源以及检索受众规模。

## 支持的用例

AI Assistant中的Audience Agent支持以下用例：

- 查找您的受众规模并检测受众规模的显着变化
   - 这让您能够找到突然增加或减少的受众，从而更好地分析潜在的市场变化
- 检测重复的受众
   - 这可以让您减少所创建受众的重复劳动
- 根据完整的或部分属性查找受众，命名为
   - 这使您能够更轻松地浏览受众清单
- 发现可用于定义受众的XDM字段
   - 凭借此技能，您可以根据上下文和相关性更轻松地识别要在受众中使用的正确字段

Audience Agent当前&#x200B;**不**&#x200B;支持以下功能：

- 基于知识的受众创建
   - 基于知识的受众创建是指根据给定的属性和事件创建受众
   - 此外，您可以在创建受众之前估计受众的潜在大小。 这样，您可以在最有效的受众准备好激活之前，快速对其进行迭代
   - 即将支持此功能
- 基于目标的受众探索
   - 通过基于目标的受众探索，您可以通过应用机器学习模型（如购买或转化倾向），发现与业务目标一致的相关数据集和用户档案。

此外，在使用Audience Agent时，您应牢记以下限制：

- Audience Agent需要至少24小时来处理您的数据
   - 例如，您&#x200B;**不能**&#x200B;有一个查询在过去24小时内查找数据。 你至少需要查看最近48小时内的信息。
- Audience Agent仅支持使用批处理分段评估的基于&#x200B;**人员**&#x200B;的受众

## 示例提示

以下示例演示了Audience Agent的示例提示和响应。

### 对话受众探索

向我展示富裕买家的栏位。

+++ 响应

![AI助手显示一个表格，其中显示与富裕买家相关的字段。](./images/audience/affluent-buyers.png)

+++

在过去30天内，哪些受众未激活或未用于任何营销活动？

+++ 响应

![AI助手显示一个表格，其中显示过去30天内未激活或未在营销活动中使用的受众。](./images/audience/not-activated.png)

+++

列出过去3个月内映射到新目标的所有受众。

+++ 响应

![AI助手列出过去3个月映射到新目标的受众。](./images/audience/new-destination.png)

+++

### 检测重复的受众

我是否具有任何描述相同或类似的受众？

+++ 响应

![AI Assistant显示一个表，其中包含区段定义和具有相同区段定义的受众的名称。](./images/audience/similar-descriptions.png)

+++

标识具有相同规则但名称不同的受众。

+++ 响应

![AI助手显示一个表，其中包含共享相同受众规则的受众的名称。](./images/audience/same-rules-different-names.png)

+++

显示具有相同规则但不同激活目标的所有受众。

+++ 响应

![AI助手显示没有指向不同目标的重复区段定义。](./images/audience/same-rules-different-destinations.png)

+++

### 检索受众规模

我的受众“加州金星会员_f153e1”的当前规模是多少？

+++ 响应

![AI助手声明所询问的受众的当前大小。](./images/audience/current-size.png)

+++

我最大的受众是什么？

+++ 响应

![AI助手提供有关配置文件最多的受众的信息，包括名称和受众ID。](./images/audience/largest-audience.png)

+++

### 检测受众规模的显着变化

上周哪些受众的规模扩大了20%以上？

+++ 响应

![AI Assistant显示一个表，其中列出了与查询匹配的所有受众的名称。 它还显示百分比增长、当前受众规模以及之前的受众规模。](./images/audience/increase-past-week.png)

+++

上个月哪些受众的大小缩减了10%以上？

+++ 响应

![AI Assistant显示一个表，其中列出了与查询匹配的所有受众的名称。 它还显示当前受众规模、以前的受众规模以及旧受众规模的日期。](./images/audience/decrease-month.png)

+++

我增长最快的受众是什么？

+++ 响应

![AI Assistant声明增长最快的受众的名称，以及当前大小和增长百分比。](./images/audience/fastest-growing.png)

+++

## 后续步骤

阅读本指南后，您应该更好地了解Audience Agent及其支持的功能。 有关Adobe Experience Platform中代理的更多信息，请阅读[Agent Orchestrator概述](./agent-orchestrator.md)。
