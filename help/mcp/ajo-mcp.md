---
title: CX Co-worker Gateway中的Adobe Journey Optimizer工具
description: 通过CX Co-worker Gateway了解哪些Adobe Journey Optimizer工具可用。
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%

---

# CX Co-worker Gateway中的Adobe Journey Optimizer工具 {#ajo-mcp}

使用Adobe Journey Optimizer产品工具从与MCP兼容的客户端检查活动和渠道配置。 当您的组织已启用，并且您的用户帐户具有所需的Journey Optimizer权限时，可以通过[CX Co-worker Gateway](overview.md)使用这些工具。

>[!AVAILABILITY]
>
>Journey Optimizer产品工具位于Beta中。 访问仅通过邀请进行，并且需要Adobe组织启用。 请参阅[访问CX Co-worker网关工具](access.md)。

## 主要功能 {#mcp-capabilities}

Journey Optimizer工具为营销活动和渠道配置审查提供了一个只读界面。 您可以：

- 列出Journey Optimizer营销活动并按状态筛选。
- 检索营销活动详细信息，包括定位、计划、渠道和内容配置元数据。
- 列出电子邮件、短信、推送和WhatsApp渠道的渠道配置。
- 无需导航产品屏幕，即可使用自然语言查看营销活动和渠道设置。

>[!IMPORTANT]
>
>当前Beta中的所有Journey Optimizer工具均为只读。 不支持创建、更新、删除、启动、停止或发布营销活动。

## 可用工具 {#mcp-tools}

| 工具 | 描述 |
| --- | --- |
| `ajo_campaign_list` | 浏览Journey Optimizer营销活动。 支持按状态筛选，如`DRAFT`、`LIVE`、`STOPPED`和`COMPLETED`。 |
| `ajo_campaign_get` | 按ID获取特定营销活动的详细信息和配置，包括受众定位、计划、渠道和内容设置元数据。 |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | 查看电子邮件、短信、推送或[!DNL WhatsApp]渠道的表面预设和品牌策略设置。 |

## 示例提示 {#mcp-use-cases}

| 目标 | 示例提示 |
| --- | --- |
| Campaign 概述 | “向我显示我的所有Journey Optimizer营销活动。” |
| 状态审核 | “哪些营销活动当前处于实时状态？” |
| 营销活动详细信息 | “获取营销活动`[campaign ID]`的完整详细信息。” |
| 受众和定位 | “营销活动`[campaign ID]`的目标受众是哪些受众？” |
| 时间表和计时 | “计划何时运行营销活动`[campaign ID]`？” |
| 故障排除 | “查看营销活动`[campaign ID]`的设置并标记可能的问题。” |
| 渠道配置 | “提供了哪些电子邮件渠道配置？” |
| 渠道审核 | “哪些渠道配置缺失或不完整？” |

## 产品上下文和权限 {#mcp-context}

您的用户帐户必须有权查看您查询的Journey Optimizer营销活动和渠道配置。 MCP不会绕过产品权限。

如果您的组织使用多个沙盒，请在需要来自特定沙盒的结果时，在提示中指定沙盒或环境上下文。

## 已知限制 {#mcp-limitations}

| 限制 | 描述 | 解决方法 |
| --- | --- | --- |
| 只读表面 | Journey Optimizer工具仅公开检索操作。 您无法创建、更新、删除、开始、停止或发布营销活动。 | 使用Journey Optimizer UI或API进行写入操作。 |
| 无参与或绩效指标 | 工具不会返回展示次数、点进率、转化率或投放统计信息等报表数据。 | 使用Journey Optimizer报表、Customer Journey Analytics工具或Adobe Analytics工具来了解性能指标。 |
| 营销活动列表分页有限 | 营销活动列表返回结果的第一页，最多可返回50个营销活动按字母顺序排序。 不应用偏移和限制值。 | 如果已知促销活动ID，则直接使用`Get Campaign`。 使用Journey Optimizer UI进行完全浏览和过滤。 |
| 无按日期、渠道或计划进行服务器端筛选 | 营销活动列表支持状态筛选，但不支持发布日期、计划日期、渠道或营销活动类型筛选。 | 使用Journey Optimizer UI促销活动列表进行本机日期和渠道筛选。 |
| 消息内容检索不可用 | 消息HTML、主题行、个性化令牌和选件内容无法通过当前工具使用。 | 直接在Journey Optimizer UI中查看消息内容和个性化。 |