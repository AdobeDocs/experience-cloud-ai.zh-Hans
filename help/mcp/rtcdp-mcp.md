---
title: Real-Time CDP MCP (Beta)
description: 了解如何使用MCP服务器将Adobe Real-Time CDP连接到MCP客户端。
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 3%

---

# CX Co-worker Gateway中的Real-Time CDP工具 {#rtcdp-mcp}

您可以使用Real-Time CDP MCP产品工具从与MCP兼容的客户端检查受众、目标、源、身份命名空间和激活运行状况。 在启用了您的组织并且您的用户帐户具有所需的Real-Time CDP权限时，可以通过统一的[CX Co-worker Gateway网关](overview.md)使用这些工具。

>[!AVAILABILITY]
>
>Real-Time CDP产品工具位于Beta中。 访问仅通过邀请进行，并且需要Adobe组织启用。 请参阅[访问CX Co-worker网关工具](access.md)。

## 主要功能 {#mcp-capabilities}

Real-Time CDP工具提供只读监控和分类界面。 您可以：

* 列出并检查受众，包括生命周期状态、来源和身份命名空间。
* 查看受众评估和导出作业以识别最近的失败。
* 检查已配置的目标帐户、目标流和激活运行历史记录。
* 检查源连接器、帐户、流和摄取运行历史记录。
* 列出身份命名空间和合并策略。

>[!IMPORTANT]
>
>当前Beta中的所有Real-Time CDP工具均为只读。 不支持创建、更新、激活或删除受众、目标、源或数据流。

## 可用工具 {#mcp-tools}

| 面积 | 工具 | 描述 |
| --- | --- | --- |
| 受众 | `search_audiences` | 按名称、实体类型、生命周期状态、身份命名空间或来源列出和查找受众。 |
| 受众 | `preview_audience_membership` | 在将PQL或SDD区段表达式另存为受众之前，估计其大小。 |
| 受众 | `inspect_audience_evaluation_jobs` | 检索区段评估作业记录以诊断受众刷新问题或确认最近的评估历史记录。 |
| 受众 | `inspect_audience_export_jobs` | 检索受众导出作业记录，以确认导出已完成或表面故障详细信息。 |
| 目标 | `search_destination_connectors` | 列出平台中可用的目标连接器类型。 |
| 目标 | `search_destination_accounts` | 列出经过身份验证的目标帐户。 |
| 目标 | `search_destination_input_connections` | 检索目标流的Experience Platform端输入。 |
| 目标 | `search_destination_output_connections` | 检索目标流的外部端点，包括目标路径、文件格式和投放配置。 |
| 目标 | `search_destination_flows` | 列出并检查已配置的目标激活流程，包括状态、映射和计划。 |
| 目标和源 | `inspect_flow_runs` | 检索源和目标流执行历史记录，包括状态、计时、记录计数和失败详细信息。 |
| 源 | `search_source_connectors` | 列出平台中可用的源连接器类型。 |
| 源 | `search_source_accounts` | 列出经过身份验证的源帐户。 |
| 源 | `search_source_input_connections` | 检索源流从帐户提取的内容。 |
| 源 | `search_source_output_connections` | 检索源流的Experience Platform数据集目标。 |
| 源 | `search_source_flows` | 列出和检查已配置的源摄取管道，包括状态、映射和计划。 |
| 身份标识 | `search_identity_namespaces` | 列出沙盒中的身份命名空间定义。 |
| 身份标识 | `search_merge_policies` | 列出控制如何汇编实时客户个人资料的合并策略记录。 |

## 示例提示 {#mcp-use-cases}

| 目标 | 示例提示 |
| --- | --- |
| 列出受众 | “在`prod`沙盒中列出我的受众。” |
| 检查受众 | “显示受众ID `abc123`的详细信息和生命周期状态。” |
| 诊断评估问题 | “向我显示最新的受众评估作业并标记失败。” |
| 检查导出作业 | “列出最近的受众导出作业，并向我显示每个作业的状态。” |
| 估计受众规模 | “在保存此PQL表达式之前，先估算其大小：`homeAddress.country = 'US'`。” |
| 查看目标设置 | “列出我的目标激活流程，并显示哪些流程已启用或已禁用。” |
| 调查失败的激活运行 | “显示流ID `xyz789`的运行历史记录并总结所有错误。” |
| 查看源摄取 | “显示源流ID `src456`的最近运行历史记录并标记失败。” |
| 检查身份配置 | “我的沙盒中配置了哪些身份命名空间？” |

## 权限 {#mcp-context}

您的Adobe组织和沙盒上下文在网关连接级别创建一次，并应用于每个工具系列，因此您不会从Real-Time CDP工具切换组织或沙盒。 要为会话设置该上下文，请参阅工具调用的[产品上下文](install.md#mcp-connect-params)。

您的用户帐户必须有权查看您查询的Real-Time CDP资源。 网关不会绕过产品权限。

## 已知限制 {#mcp-limitations}

| 限制 | 描述 | 解决方法 |
| --- | --- | --- |
| 只读表面 | Real-Time CDP工具仅公开retrieve API。 您无法创建、更新、激活或删除受众、目标、源或数据流。 | 使用Real-Time CDP UI或Experience Platform API进行写入操作。 |
| 无参与或投放量度 | 工具不会从目标平台返回下游投放统计信息、参与度或转化量度。 | 使用目标平台的报表、Customer Journey Analytics工具或Adobe Analytics工具获取参与和转化数据。 |
| 区段查询必须在外部创作 | `preview_audience_membership`需要有效的PQL或SDD表达式。 此工具不会为您编写查询。 | 在区段生成器或分段服务API中创作表达式，然后将其粘贴到提示符下。 |
| 通过继续令牌进行分页 | 列表工具返回分页结果。 超大沙盒中的完整枚举需要链接继续令牌。 | 使用名称、状态、连接规范或时间范围等过滤器缩小查询范围。 |
| 激活运行筛选仅基于时间 | 激活运行检查支持按状态和完成时间戳进行筛选，但不支持直接按错误类型或目标平台进行筛选。 | 首先按`flowId`筛选，以将运行范围限定到特定目标流。 |

