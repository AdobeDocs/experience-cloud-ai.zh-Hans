---
title: Adobe CX Enterprise MCP中的Adobe Analytics工具
description: 了解可通过Adobe CX Enterprise MCP使用哪些Adobe Analytics工具。
source-git-commit: df05761a8555950366fcaa201ce9c0fd47bb0802
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Adobe CX Enterprise MCP中的Adobe Analytics工具 {#aa-mcp}

您可以使用Adobe Analytics工具从与MCP兼容的客户端浏览报表包、发现维度和量度、运行报表以及管理选定的分析组件。 当您的帐户具有所需的Adobe Analytics许可证和权限时，可通过统一的[Adobe CX Enterprise MCP](overview.md)使用这些工具。

>[!AVAILABILITY]
>
>拥有Adobe Analytics许可证的客户可以使用Analytics工具。 访问由Adobe Admin Console中的&#x200B;**MCP访问**&#x200B;权限控制。 有关详细信息，请阅读[访问CX Enterprise MCP工具](access.md)。

## 主要功能 {#mcp-capabilities}

Adobe Analytics工具支持来自MCP客户端的Analytics发现和报告工作流。 您可以：

- 发现报表包并检查其配置方式。
- 查找维度、量度、计算量度、区段、日期范围和工作区项目。
- 使用维度、量度、日期范围和区段过滤器运行排名报表和趋势报表。
- 创建和更新选定的可重用组件，如区段和日期范围。
- 使用自然语言从Adobe Analytics数据生成见解。

>[!IMPORTANT]
>
>某些Adobe Analytics工具可以创建或更新Analytics组件。 查看并验证所有MCP启动的更改，然后再依赖它们。

## 工具覆盖率 {#mcp-tools}

| 面积 | 您可以做什么 |
| --- | --- |
| 报表包 | 发现可用于您的帐户的报表包并检查配置详细信息。 |
| 组件 | 查找并描述维度、量度、计算量度、区段和日期范围。 |
| 报表 | 使用选定的维度、量度、日期范围和区段过滤器运行排名报表和趋势报表。 |
| 区段和日期范围 | 创建和更新您的产品权限允许的可重用区段和日期范围。 |
| Workspace项目 | 发现和描述Analysis Workspace项目。 |

有关完整的当前工具列表，请参阅[Adobe Analytics MCP工具引用](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}。

## 示例提示 {#mcp-use-cases}

| 目标 | 示例提示 |
| --- | --- |
| 发现报表包 | “列出我可以访问的报表包。” |
| 查找组件 | “查找与收入相关的量度。” |
| 运行报表 | “运行过去7天内按页面显示的页面查看次数的排名报表。” |
| 检查区段 | “描述区段`[segment name]`并显示其定义。” |
| 浏览项目 | “列出与客户获取相关的Analysis Workspace项目。” |

## 产品上下文和权限 {#mcp-context}

您的帐户必须属于Adobe Analytics产品配置文件，该配置文件包含由Adobe Admin Console中的系统或产品管理员授予的&#x200B;**MCP访问权限**&#x200B;权限项。

产品权限仍然适用。 您的帐户必须能够查看您查询的报表包、组件、报表和项目，并且必须具有适当的产品权限来执行写入操作，例如创建或更新可重用组件。

## 更多信息 {#mcp-more}

有关完整的工具参考和入门指南，请参阅[Adobe Analytics MCP文档](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}。