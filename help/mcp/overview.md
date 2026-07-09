---
title: Adobe CX Enterprise MCP服务器
description: Adobe CX Enterprise MCP Server是适用于Adobe CX Enterprise的统一MCP，它为MCP客户端提供了到支持的产品工具的单一连接。
source-git-commit: b40034bdc866a2737b909386b79c028793f324cb
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 4%

---

# Adobe CX Enterprise MCP服务器 {#mcp-overview}

Adobe CX Enterprise MCP Server是适用于Adobe CX Enterprise的统一模型上下文协议(MCP)。 通过一个连接，与MCP兼容的客户端可以访问您的组织和帐户有权使用的Adobe产品工具。

>[!IMPORTANT]
>
>在使用CX Enterprise MCP工具之前，必须启用Adobe组织。 如果贵组织还没有访问权限，请联系您的Adobe客户团队以请求对贵组织进行启用。

对所有MCP客户端设置使用CX Enterprise端点：

```
https://cx-enterprise.adobe.io/mcp
```

连接后，端点会公开可用于您的Adobe组织和凭据的工具。 本指南中特定于产品的页面描述了每个产品工具可执行的操作、可访问的数据以及任何特定于产品的限制。

## 什么是模型上下文协议？ {#mcp-what-is}

MCP（Model Context Protocol，模型上下文协议）是一种用于将AI应用程序连接到外部系统的开源标准。 与MCP兼容的客户端（如[!DNL Claude]、[!DNL ChatGPT]、[!DNL Cursor]、[!DNL Claude Code]、[!DNL Codex]和[!DNL VS Code]）可以使用这些工具检索产品上下文、运行支持的操作并以自然语言返回答案。

CX Enterprise为CX Enterprise产品工具提供了一个受控制的端点。 只需连接到端点并使用为您的授权解决方案呈现的产品工具，而无需添加单独的产品服务器。

## 可用的产品工具 {#available-product-tools}

本指南中记录了以下产品工具：


| 产品工具 | 通过端点公开的内容 | 可用性 | 文档 |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | 受众、目标、源、身份命名空间和激活运行状况（只读） | Beta | [Real-Time CDP工具](rtcdp-mcp.md) |
| **Experience Platform** | 架构、数据集、数据管理、查询服务和审核事件（只读） | Beta | [Experience Platform工具](aep-mcp.md) |
| **Journey Optimizer** | 营销活动和渠道配置（只读） | Beta | [Journey Optimizer工具](ajo-mcp.md) |
| **Customer Journey Analytics** | 数据视图、维度、量度、报表、区段、日期范围、项目和受众（读写） | 可用 | [Customer Journey Analytics工具](cja-mcp.md) |
| **Adobe Analytics** | 报表包、维度、量度、报表、区段、日期范围和工作区项目（读取和写入支持的组件） | 可用 | [Adobe Analytics工具](analytics-mcp.md) |
| **Workfront** | 项目、任务和审批工作流的工作管理工具 | 预览 | [Workfront MCP服务器](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>工具可用性取决于您的产品许可证、组织支持、产品权限以及用于身份验证的Adobe凭据。 MCP仅显示您的组织和用户帐户有权访问的工具。 请参阅[访问CX Enterprise MCP工具](access.md)。



## 快速入门 {#mcp-get-started}

1. 查看[访问CX Enterprise MCP工具](access.md)以确认产品的可用性、启用和权限。
2. 按照[安装Adobe for CX Enterprise MCP](install.md)将MCP客户端连接到终结点。
3. 查看您计划使用的每个产品工具的产品页面。

