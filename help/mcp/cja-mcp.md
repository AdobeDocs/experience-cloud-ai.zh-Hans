---
title: Adobe CX Enterprise MCP中的Customer Journey Analytics工具
description: 了解可通过Adobe CX Enterprise MCP使用哪些Adobe Customer Journey Analytics工具。
source-git-commit: 6c73b4d2e452a82597565d71279df2dba605a977
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# Adobe CX Enterprise MCP中的Customer Journey Analytics工具 {#cja-mcp}

使用Customer Journey Analytics产品工具浏览数据视图，发现维度和量度，运行报表，以及从与MCP兼容的客户端管理选定的分析组件。 当您的帐户具有所需的Customer Journey Analytics许可证和权限时，可以通过[CX Enterprise MCP](overview.md)使用这些工具。

>[!AVAILABILITY]
>
>拥有Customer Journey Analytics许可证的客户可以使用Customer Journey Analytics工具。 访问由Adobe Admin Console中的&#x200B;**MCP访问**&#x200B;权限控制。 请参阅[访问CX Enterprise MCP工具](access.md)。

## 主要功能 {#mcp-capabilities}

Customer Journey Analytics工具支持从MCP客户端管理分析工作流。 您可以：

* 发现数据视图并检查其配置方式。
* 查找维度、量度、计算量度、区段、日期范围、受众和项目。
* 使用维度、量度、日期范围和区段过滤器运行排名报表和趋势报表。
* 检查组件定义和组件使用情况。
* 创建或更新选定的Analytics组件和工作区项目。

>[!IMPORTANT]
>
>与只读[Real-Time CDP](rtcdp-mcp.md)、[Experience Platform](aep-mcp.md)和[Journey Optimizer](ajo-mcp.md)产品工具不同，Customer Journey Analytics工具包含写入操作。 他们可以创建和更新区段、计算量度、日期范围、项目和受众。 查看并验证所有MCP启动的更改，然后再依赖它们。

## 可用工具 {#mcp-tools}

| 面积 | 工具 | 描述 |
| --- | --- | --- |
| 设置和指南 | `describeCja` | 返回工具、维度、量度、区段、计算量度和项目结构的参考指南。 |
| 设置和指南 | `setDefaultSessionDataViewId` | 为后续工具调用配置会话级别的默认数据视图。 |
| 发现 | `findDimensions` | 查找支持语义搜索的可用维度。 |
| 发现 | `findMetrics` | 发现标准和自定义指标，但不包括计算指标。 |
| 发现 | `findCalculatedMetrics` | 浏览用户创建和共享的计算指标。 |
| 发现 | `findSegments` | 列出当前用户可访问的区段。 |
| 发现 | `findDateRanges` | 检索已保存的日期范围组件。 |
| 发现 | `findDataViews` | 发现可用的数据视图。 |
| 发现 | `findProjects` | 查找工作区项目。 |
| 发现 | `findAudiences` | 列出可用的受众组件。 |
| 报告和分析 | `runReport` | 执行包含维度、量度、日期范围和可选区段过滤器的排名报表。 |
| 报告和分析 | `searchDimensionItems` | 检索划分报表所需的维度值。 |
| 组件详细信息 | `describeDimension` | 显示特定维度的详细元数据。 |
| 组件详细信息 | `describeMetric` | 返回量度元数据和测量详细信息。 |
| 组件详细信息 | `describeSegment` | 显示区段的定义和兼容性信息。 |
| 组件详细信息 | `describeCalculatedMetric` | 显示使用的公式和基本量度。 |
| 组件详细信息 | `describeProject` | 详细介绍Workspace项目的配置。 |
| 组件详细信息 | `describeAudience` | 返回受众元数据和发布状态。 |
| 组件使用 | `listComponentUsage` | 按使用频率对组件进行排名。 |
| 组件使用 | `listFrequentlyUsedWith` | 标识通常配对在一起的组件。 |
| 组件使用 | `listSimilarTo` | 查找用于类似目的的替代组件。 |
| 创建和更新 | `upsertSegment` | 创建新区段或修改现有区段。 |
| 创建和更新 | `upsertCalculatedMetric` | 创建新的计算量度或修改现有计算量度。 |
| 创建和更新 | `createDateRange` | 创建可重复使用的日期范围组件。 |
| 创建和更新 | `upsertProject` | 创建新的工作区项目或修改现有的工作区项目。 |
| 创建和更新 | `upsertAudience` | 创建新的受众定义或修改现有受众定义。 |

## 示例提示 {#mcp-use-cases}

| 目标 | 示例提示 |
| --- | --- |
| 列出数据视图 | “列出Customer Journey Analytics中可供我使用的数据视图。” |
| 发现组件 | “在数据视图`[data view name]`中查找与收入相关的量度。” |
| 运行报表 | “按月份运行上一季度的趋势订单报表。” |
| 划分量度 | “按访问次数显示前10个营销渠道，并按设备类型细分。” |
| 检查组件 | “描述区段`[segment name]`并显示其定义。” |
| 审核使用情况 | “我的项目中最常使用哪些维度？” |
| 创建区段 | “为过去30天内查看过定价页面的用户创建一个区段。” |

## 产品上下文和权限 {#mcp-context}

您的帐户必须属于Customer Journey Analytics产品配置文件，该配置文件包含由Adobe Admin Console中的系统或产品管理员授予的&#x200B;**MCP访问权限**&#x200B;权限项。

产品权限仍然适用。 您的帐户必须能够查看您查询的数据视图、组件、项目和受众，并且必须具有适当的产品权限来执行写入操作，例如创建或更新区段、计算量度、日期范围、项目或受众。

## 观看实际操作 {#mcp-videos}

**概述**

>[!VIDEO](https://video.tv.adobe.com/v/3486313/?learn=on&enablevpops)

**操作中**

>[!VIDEO](https://video.tv.adobe.com/v/3486314/?learn=on&enablevpops)

## 更多信息 {#mcp-more}

有关完整的工具参考和入门指南，请参阅[Customer Journey Analytics MCP文档](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}。