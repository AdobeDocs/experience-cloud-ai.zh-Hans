---
title: CX Enterprise MCP中的会话上下文工具
description: 了解为所有CX Enterprise MCP工具调用设置组织、沙盒和数据视图上下文的核心工具。
source-git-commit: 023a4c15ca787c9b110b52914fd18d0e6eecd23d
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Adobe CX Enterprise MCP中的会话上下文工具 {#mcp-core}

Adobe CX Enterprise MCP包括一组会话上下文工具，用于建立所有其他产品工具都在其中运行的Adobe组织、Adobe Experience Platform沙盒和Customer Journey Analytics数据视图。 无需其他许可证或支持 — 在连接到[CX Enterprise MCP服务器](overview.md)后，每个经过身份验证的用户都可以使用这些工具。

## 上下文的工作方式 {#mcp-core-how}

CX Enterprise MCP将每个工具调用范围限定到一个活动的Adobe组织。 除此之外，上下文要求取决于产品：

- **基于Experience Platform的产品** — [Real-Time CDP](rtcdp-mcp.md)、[Experience Platform](aep-mcp.md)和[Journey Optimizer](ajo-mcp.md)工具在Experience Platform沙盒中运行。 与`core-set_sandbox`的每个会话均设置一次沙盒；所有三个会话都共享该沙盒。
- **其他产品** — 未在Experience Platform上构建的产品不使用沙盒上下文。 例如，[Customer Journey Analytics](cja-mcp.md)工具针对数据视图进行解析，[Adobe Analytics](analytics-mcp.md)工具针对报表包进行解析。

在会话开始时设置一次上下文 — 单个产品工具在会话期间不会切换组织、沙盒或数据视图。

## 可用工具 {#mcp-core-tools}

| 工具 | 描述 |
| --- | --- |
| `core-list_orgs` | 列出经过身份验证的用户可访问的Adobe组织。 返回每个组织的显示名称和`@AdobeOrg`标识符。 使用此项在调用`core-switch_org`之前查找组织ID。 |
| `core-switch_org` | 为会话设置活动的Adobe组织。 所有后续工具调用的范围都限制在此组织内，直到会话结束或组织再次切换为止。 |
| `core-list_sandboxes` | 列出活动组织中可用的Experience Platform沙箱。 返回每个沙盒的名称、标题、类型（生产或开发）和状态。 使用此选项在调用`core-set_sandbox`之前查找沙盒名称。 |
| `core-set_sandbox` | 为会话设置活动的Experience Platform沙盒。 Real-Time CDP、Experience Platform和Journey Optimizer工具将其数据范围限定在此沙盒中。 |
| `core-list_dataviews` | 列出当前上下文中经过身份验证的用户可用的Customer Journey Analytics数据视图。 返回数据视图ID和显示名称。 使用此项在调用`core-set_dataview`之前查找数据视图。 |
| `core-set_dataview` | 设置会话的默认Customer Journey Analytics数据视图。 设置后，需要数据视图的CJA工具（如`findDimensions`、`findMetrics`和`runReport`）将自动使用此值，除非在单个工具调用中指定了其他数据视图。 |

## 典型会话设置 {#mcp-core-setup}

在调用产品工具之前，在会话开始时设置上下文：

1. **组织** — 调用`core-list_orgs`列出可访问的组织，然后调用`core-switch_org`列出目标组织ID。
2. **沙盒** — 如果您计划使用Real-Time CDP、Experience Platform或Journey Optimizer工具，请调用`core-list_sandboxes`以列出可用的沙盒，然后使用目标沙盒名称`core-set_sandbox`。
3. **数据视图** （仅限CJA） — 如果您计划使用Customer Journey Analytics工具，请调用`core-list_dataviews`以列出可用的数据视图，然后使用您选择的数据视图`core-set_dataview`。

您可以要求MCP客户端在单个自然语言请求中完成此设置：

> “在此会话中使用组织`1234ABCD@AdobeOrg`、沙盒`prod`和数据视图`My Company — Global`。”

客户端将调用相应的工具，并在设置上下文后进行确认。

>[!TIP]
>
>如果您的Adobe凭据仅属于一个组织，则`core-list_orgs`和`core-switch_org`仍然有效，但无论如何有效组织将相同。 如果您计划使用Real-Time CDP、Experience Platform或Journey Optimizer工具，则仍需要调用`core-set_sandbox`；如果您计划使用Customer Journey Analytics工具，则仍需要调用`core-set_dataview`。

## 示例提示 {#mcp-core-examples}

| 目标 | 示例提示 |
| --- | --- |
| 发现可用的组织 | “我可以访问哪些Adobe组织？” |
| 设置组织上下文 | “切换到组织`My Org (1234ABCD@AdobeOrg)`。” |
| 发现可用的沙盒 | “列出我当前组织中可用的沙盒。” |
| 设置沙盒上下文 | “对此会话使用`prod`沙盒。” |
| 发现可用的数据视图 | “我可以访问哪些Customer Journey Analytics数据视图？” |
| 设置数据视图上下文 | “将`My Company — Global`设置为默认数据视图。” |
| 完整会话设置 | “使用组织`1234ABCD@AdobeOrg`、沙盒`prod`和数据视图`My Company — Global`设置会话。” |

## 相关页面 {#mcp-core-related}

- [安装Adobe CX Enterprise MCP](install.md) — 如何连接MCP客户端，包括产品上下文设置部分。
- [访问CX Enterprise MCP工具](access.md) — 按产品列出的访问要求。