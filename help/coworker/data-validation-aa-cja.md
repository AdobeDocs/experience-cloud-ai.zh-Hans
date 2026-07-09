---
title: 从Adobe Analytics升级到Customer Journey Analytics时与同事验证数据
description: 了解Analytics管理员如何在迁移期间使用CX Enterprise Co-worker数据验证技能比较Adobe Analytics和Customer Journey Analytics数据。
hold: true
source-git-commit: 850bfef76e3c3e081f9860b9757e5e5128383f76
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# 从Adobe Analytics升级到Customer Journey Analytics时与同事验证数据

CX Enterprise Co-worker包括验证技能，允许您在从Adobe Analytics升级到Customer Journey Analytics时验证数据。 数据验证在单个会话中完成。

此技能会自动比较：

* 每个维度、量度和趋势会分别在不同的实施中进行。

* 所有Adobe Analytics报表包针对所有Customer Journey Analytics数据视图。

进行这些比较后，该技能会生成人工智能驱动的洞察和建议，您可以实施这些洞察和建议来帮助您升级到Customer Journey Analytics。

## 开始之前

要在升级过程中验证数据，您需要：

* 要验证的Adobe Analytics报表包。

* 包含相同数据的Customer Journey Analytics数据视图。

您无需提前知道如何构建实施。 该技能会自动检测数据是通过Analytics Source Connector映射，还是通过两个并排实施映射，因此您无需自己提供该上下文。

## 启动验证会话

1. 登录到CX Enterprise Co-worker。

1. 选择&#x200B;[!UICONTROL **新建聊天**]。

1. 在文本字段中，提示代理验证从Adobe Analytics到Customer Journey Analytics的迁移：

   **提示**

   > 帮助我验证我的公司是否已从Adobe Analytics升级到Customer Journey Analytics。

   您的请求将被路由到数据验证技能，该技能将启动交互式设置过程。

1. 设置过程包括下表中的问题。 对于每个问题，请选择答案，然后选择&#x200B;[!UICONTROL **提交**]。

   | 问题 | 其他上下文 |
   |---------|----------|
   | [!UICONTROL **选择您的Analytics公司**] | 这是您的Adobe Analytics登录公司。 |
   | [!UICONTROL **选择您的报表包**]<!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | 这是Adobe Analytics中的报表包，其中包含要针对Customer Journey Analytics数据验证的数据。 |
   | [!UICONTROL **选择您的Customer Journey Analytics数据视图**] | 这是Customer Journey Analytics中的数据视图，其中包含与您选择的Adobe Analytics报表包相同的数据。 |

1. 查看设置摘要，确认您正在验证正确的数据，然后再继续。 摘要包括您选择的公司、报表包和数据视图，以及每个系统中排名最前的量度和维度的预览。

1. 继续下面的部分，[选择要验证的数据](#choose-the-data-to-validate)。

## 选择要验证的数据

您可以验证单个量度或维度，也可以验证报表包和数据视图中包含的所有量度和维度。

1. 从以下选项中选择：

   | 验证选项 | 描述 |
   |---------|----------|
   | [!UICONTROL **单个量度比较**] | 比较Adobe Analytics和Customer Journey Analytics之间某个量度的趋势。 当您希望快速检查特定量度（如页面查看次数或访问次数）时，可使用此选项。 |
   | [!UICONTROL **单个维度比较**] | 在Adobe Analytics和Customer Journey Analytics之间比较单个维度的细分。 当您怀疑特定维度的映射或分类差异时，请使用此选项。 |
   | [!UICONTROL **完整的报表包和数据视图审核**] | 在一次运行中比较最多20个量度和维度。 当您希望全面了解迁移的整体运行状况时，可使用此选项。 |

1. 继续下面的部分，[审阅分析](#review-the-analysis)。

## 查看分析

1. 选择以下每个选项卡以查看分析：

   | “分析复查”选项卡 | 描述 |
   |---------|----------|
   | [!UICONTROL **总体匹配率**] | 一个百分比，指示Adobe Analytics报表包中的数据与Customer Journey Analytics数据视图的数据匹配程度。 |
   | [!UICONTROL **关键见解**] | 在分析期间发现的关键见解。 |
   | [!UICONTROL **概要**] | Adobe Analytics总计、Customer Journey Analytics总计、总差异、通过天数和关键天数。<!--what are these?--> |
   | [!UICONTROL **每日趋势**] | 显示Adobe Analytics数据与Customer Journey Analytics数据的并排比较的图形。 |
   | [!UICONTROL **每日详细信息**] | <!--what goes here?--> |

1. 在分析中向下滚动以查看在分析期间发现的其他模式、这些模式的可能原因以及为解决任何数据差异可采取的建议操作。

1. 验证建议的操作是否有效，然后在Adobe Experience Platform或Adobe Analytics中解析它们。

1. （可选）通过分析其他量度、分析其他维度或运行另一个最多包含20个量度和维度的报表来继续您的分析，如[选择要验证的数据](#choose-the-data-to-validate)中所述。

