---
title: Audience 代理
description: 了解如何使用Audience Agent创建受众、查看受众更改、检测重复的受众以及查看受众分析。
source-git-commit: ca3766477459fb13170d176057a3ea9fbb791b29
workflow-type: tm+mt
source-wordcount: '1204'
ht-degree: 2%

---


# Audience 代理

>[!AVAILABILITY]
>
>Audience Agent适用于有权访问AI Assistant的所有客户。 但是，您需要以下权限才能完全使用Audience Agent功能。
>
>**查看区段**：此权限允许您使用Audience Agent直接在AI助手中查看受众分析。
>
>**管理区段**：“收件人”权限允许您使用Audience Agent直接在AI助手中创建新受众。

通过Audience Agent，您可以查看有关受众的分析，包括检测受众规模的显着变化、检测重复的受众、探索受众资源以及检索受众规模。

>[!SLIDE](audience-agent-overview)

## 支持的用例

AI Assistant中的Audience Agent支持以下用例：

- 对话式浏览您的受众
   - 查找现有受众的受众规模
   - 查找基于完整或部分属性的受众，命名为
   - 检测重复的受众
   - 发现可用于定义受众的XDM字段
- 检测受众规模的显着变化
   - 这让您能够找到突然增加或减少的受众，从而更好地分析潜在的市场变化
- 受众创建
   - 凭借此技能，您可以根据给定的属性和事件创建受众
   - 此外，通过这项技能，可在创建受众之前估计受众的潜在大小，从而可在最有效的受众准备好激活之前快速对其进行迭代

<!-- - Find your audience size and detect significant changes in audience size
  - This lets you find audiences that have suddenly grown or shrunk, letting you better analyze potential market changes
- Detect duplicate audiences
  - This lets you reduce redundancies with your created audiences
- Find audiences based on full or partial attributes named
  - This lets you more easily navigate through your audience inventory
- Discover XDM fields you can use to define an audience
  - This skill lets you more easily identify the right fields to use in your audience based on context and relevance -->

Audience Agent当前&#x200B;**不**&#x200B;支持以下功能：

- 基于目标的受众探索
   - 通过基于目标的受众探索，您可以通过应用机器学习模型（如购买或转化倾向），发现与业务目标一致的相关数据集和用户档案。

此外，在使用Audience Agent时，您应牢记以下限制：

- Audience Agent需要至少24小时来处理您的数据
   - 例如，您&#x200B;**不能**&#x200B;有一个查询在过去24小时内查找数据。 你至少需要查看最近48小时内的信息。
- Audience Agent仅支持以下受众类型：
   - 使用批处理分段评估的&#x200B;**基于人员的**&#x200B;受众
   - 针对以下用例的&#x200B;**基于帐户的**&#x200B;受众：
      - 对话受众探索
      - 重复受众检测

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

哪个帐户受众拥有最大的受众规模，该规模是多少？

+++ 响应

![AI Assistant显示一个表，其中显示了最大的帐户受众。](./images/audience/largest-account-audience.png)

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

识别具有相同规则但名称不同的帐户受众。

+++ 响应

![AI助手显示一个表，其中包含共享相同受众规则的帐户受众的名称和ID。](./images/audience/duplicate-account-audience.png)

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

### 创建受众

使用Audience Agent创建受众时，AI助手将指导您完成计划。 例如，您可以请求“创建一个由住在加利福尼亚的人组成的受众”。 然后，AI Assistant会列出创建受众的计划。

+++ 响应

![AI助手显示创建受众的计划。](./images/audience/audience-create-plan.png)

+++

该计划包括三个步骤：

1. [识别受众特征](#identify)
2. [估计受众规模](#estimate)
3. [创建并保留新受众](#create)

#### 识别受众特征 {#identify}

![计划的步骤1，用于识别受众特征。](./images/audience/plan-step-1.png){align="center" width="80%"}

接受计划后，AI Assistant将根据您的初始查询获取受众特征。

+++ 响应

![基于用户查询的受众定义。](./images/audience/audience-create-definition.png)

对于此查询，AI Assistant会生成相关的Profile Query Language (PQL)，以查找居住在加利福尼亚的人员。 在此使用案例中，PQL查询将如下所示：

```sql
homeAddress.state.equals("California", false)
```

有关PQL的更多信息，请阅读[PQL概述](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/pql/overview)。

+++

如果AI助手的受众定义正确，则可以批准并继续下一步骤。

#### 估计受众规模 {#estimate}

![计划的步骤2，用于估计潜在受众的大小。](./images/audience/plan-step-2.png){align="center" width="80%"}

在批准识别的受众特征后，AI助手将估计潜在受众的大小和受众定义详细信息。

+++ 响应

![显示潜在受众的样本估计值。 将显示估计的大小和区段定义。](./images/audience/audience-create-estimate.png)

+++

如果预计的大小看起来正确，您可以批准并继续下一步骤。

#### 创建和保留新受众 {#create}

![计划的步骤3，即完成创建受众。](./images/audience/plan-step-3.png){align="center" width="80%"}

最后，如果特征和受众规模看起来是正确的，则可以批准或拒绝受众的创建。

+++ 响应

首先，您可以通过提供的数据网格查看建议的受众。

![将显示审核屏幕。](./images/audience/audience-create-review.png)

如果受众看起来是正确的，您可以通过选择&#x200B;**[!UICONTROL 创建]**&#x200B;来接受建议，以完成创建受众。

![显示受众的完整建议。](./images/audience/audience-create-proposal.png)

+++

现已创建受众。

![已接受受众建议，并且已创建受众。](./images/audience/audience-finish-create.png){align="center" width="80%"}

## 后续步骤

阅读本指南后，您应该更好地了解Audience Agent及其支持的功能。 有关Adobe Experience Platform中代理的更多信息，请阅读[Agent Orchestrator概述](./agent-orchestrator.md)。

