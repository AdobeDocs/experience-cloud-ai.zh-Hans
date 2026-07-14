---
title: 访问CX Co-worker Gateway工具
description: 在使用Adobe CX Co-worker Gateway工具之前，请确认产品可用性、组织启用和权限。
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 3%

---

# 访问CX Co-worker Gateway工具 {#mcp-access}

Adobe CX Enterprise通过单个MCP公开产品工具。 访问权由产品工具评估：必须为相关的产品工具启用Adobe组织，并且您的用户帐户必须具有查看或更改这些工具公开的产品数据所需的产品权限。

>[!IMPORTANT]
>
>在使用CX Co-worker Gateway工具之前，必须启用Adobe组织。 如果贵组织还没有访问权限，请联系您的Adobe客户团队以请求对贵组织进行启用。

## 访问要求 {#mcp-requirements}


| 产品工具 | 可用性 | 访问要求 |
| --- | --- | --- |
| Real-Time CDP | Beta | 有效的Real-Time CDP许可证、Adobe组织的Beta支持，以及查看您查询的受众、目标、源、身份和激活资源的权限。 |
| Experience Platform | Beta | 有效的Experience Platform许可证、Adobe组织的Beta支持，以及查看您查询的架构、数据集、治理、查询服务、审核和沙盒资源的权限。 |
| Journey Optimizer | Beta | 有效的Journey Optimizer许可证、Adobe组织的Beta支持，以及查看活动和渠道配置的权限。 |
| Customer Journey Analytics | 可用 | 有效的Customer Journey Analytics许可证和产品配置文件，包括Adobe Admin Console中的&#x200B;**MCP访问**&#x200B;权限项。 产品权限仍可控制您可以访问或修改的数据视图、组件、报表、项目和受众。 |
| Adobe Analytics | 可用 | 有效的Adobe Analytics许可证和产品配置文件，包括Adobe Admin Console中的&#x200B;**MCP访问**&#x200B;权限项。 产品权限仍可控制您可以访问或修改的报表包、组件、报表、区段、日期范围和项目。 |
| Workfront | 预览 | 活动的Workfront许可证和Workfront MCP启用。 请参阅[Workfront MCP文档](https://experienceleague.adobe.com/zh-hans/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview)。 |


>[!NOTE]
>
>MCP仅显示您的组织和凭据有权使用的工具。 如果登录后缺少产品工具，请确认产品许可、组织启用和用户权限。

## 请求访问 {#mcp-request}

对于Beta或限量版产品工具，请联系您的Adobe客户代表，并指定要使用的Adobe for CX Co-worker Gateway产品工具。 您的代表可以协调产品启用，并在您的Adobe组织准备好时进行确认。

对于使用&#x200B;**MCP访问**&#x200B;权限项的常用产品工具，请要求系统或产品管理员将您的帐户添加到包含MCP访问权限的产品配置文件中。

## 产品内支持 {#mcp-product-enablement}

除MCP访问之外，某些产品还需要产品内启用或产品特定的权限。 例如：

- Adobe Analytics和Customer Journey Analytics需要Adobe Admin Console中的&#x200B;**MCP访问**&#x200B;权限项。
- Workfront MCP工具可通过Workfront设置启用。
- Beta产品工具需要先启用Adobe组织，然后才能通过MCP显示其工具。

查看产品页面，了解您计划用于特定产品的权限、上下文要求和限制的产品工具。

## 安装之前 {#mcp-prerequisites}

在连接MCP客户端之前，请确认：

- 已为您的Adobe组织启用所需的产品工具。
- 您的用户帐户拥有计划使用的数据和操作所需的产品权限。
- 您有权访问支持的MCP客户端，如[!DNL Claude]、[!DNL ChatGPT]、[!DNL Cursor]、[!DNL Claude Code]、[!DNL Codex]或[!DNL VS Code]。
- 对于企业安装，您或同事可以在MCP客户端的组织设置中管理连接器或自定义应用程序。

下一步： [安装Adobe CX Co-worker网关](install.md)。