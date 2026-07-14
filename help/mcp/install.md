---
title: 安装Adobe CX Co-worker网关
description: 了解如何将与MCP兼容的客户端连接到Adobe CX Co-worker网关。
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---

# 安装Adobe CX Co-worker网关 {#mcp-install}

阅读本指南，了解如何将与MCP兼容的客户端连接到Adobe CX Co-worker Gateway。  CX Co-worker Gateway对所有有文档记录的产品工具使用一个端点：

```
https://cx-coworker-gateway.adobe.io/mcp
```

安装之前，请确认您的组织和用户帐户可以访问所需的产品工具。 请参阅[访问CX Co-worker网关工具](access.md)。

## 安装工作原理 {#mcp-install-how}

CX Co-worker Gateway使用远程HTTP传输和基于浏览器的Adobe登录流程。 在每个受支持的客户端中，安装模式都相同：

1. 添加终结点URL： `https://cx-coworker-gateway.adobe.io/mcp`。
2. 保存或启用连接。
3. 在客户端首次调用工具时，完成基于浏览器的Adobe登录。
4. 设置会话的产品上下文（如果您的工具需要） — 组织所有产品，为基于Experience Platform的工具设置沙盒，并为Customer Journey Analytics设置数据视图。 查看工具调用的[产品上下文](#mcp-connect-params)。

>[!NOTE]
>
>在MCP客户端配置中不需要任何API密钥、持有者令牌、客户端密钥或其他标头。 首次使用时通过Adobe登录流程处理身份验证。

## 企业安装（管理员管理） {#mcp-install-enterprise}

大多数团队和企业MCP客户端计划要求管理员为组织添加自定义连接器。 在这些环境中，安装分为两个步骤：

1. 管理员为组织添加一次CX Co-worker Gateway端点。
2. 每个用户都使用自己的Adobe凭据启用连接器并登录。

### 步骤1：管理员添加端点 {#mcp-install-enterprise-admin}

管理员在客户端的组织设置中添加`https://cx-coworker-gateway.adobe.io/mcp`作为自定义连接器或远程MCP服务器。 确切的位置取决于客户端。

#### Claude团队和企业 {#mcp-install-enterprise-claude}

在[!DNL Claude]团队和企业计划中，组织级别的连接器由工作区&#x200B;**所有者**&#x200B;或&#x200B;**主要所有者**&#x200B;管理。

1. 以&#x200B;**所有者**&#x200B;或&#x200B;**主要所有者**&#x200B;的身份登录到[!DNL Claude]。
2. 转到&#x200B;**设置** > **管理** > **连接器**。 在某些计划中，它显示为&#x200B;**组织设置** > **连接器**。
3. 选择&#x200B;**添加自定义连接器**。
4. 输入`https://cx-coworker-gateway.adobe.io/mcp`作为服务器URL，并使用可识别的名称，如“Adobe for CX Co-worker Gateway”。
5. 保存连接器。

#### ChatGPT团队和企业 {#mcp-install-enterprise-chatgpt}

在[!DNL ChatGPT]团队和企业工作区中，连接器由工作区管理员添加。

1. 以工作区管理员身份登录到[!DNL ChatGPT]。
2. 转到&#x200B;**设置** > **连接器**。 在某些计划中，它显示为&#x200B;**设置** > **应用和连接器**。
3. 选择&#x200B;**添加连接器**。
4. 输入`https://cx-coworker-gateway.adobe.io/mcp`作为服务器URL。
5. 保存连接器。 根据您的工作区配置，此步骤可能需要启用开发人员模式或授予工作区级别的批准。

#### 其他组织管理的客户端 {#mcp-install-enterprise-other}

对于支持组织管理的远程连接器的其他客户端，请使用`https://cx-coworker-gateway.adobe.io/mcp`将CX Co-worker Gateway添加为远程HTTP MCP服务器。 除非您的客户端需要占位符值，否则将可选标头、持有者令牌字段、客户端ID字段和客户端密钥字段保留为空。

### 步骤2：用户启用连接器 {#mcp-install-enterprise-user}

管理员添加CX Co-worker Gateway后，每个用户都为其自己的帐户启用它：

1. 在客户端中打开个人连接器、应用程序或MCP设置。
2. 找到CX Co-worker Gateway连接器并启用它。
3. 开始对话，调用某个Adobe工具，然后在出现提示时完成基于浏览器的Adobe登录。
4. 设置会话的产品上下文（如果您的工具需要） — 组织所有产品，为基于Experience Platform的工具设置沙盒，并为Customer Journey Analytics设置数据视图。 查看工具调用的[产品上下文](#mcp-connect-params)。

当管理员已经为组织添加了连接器时，用户无需输入URL本身。

## 单独安装（自助服务） {#mcp-install-individual}

如果您使用单个计划、本地配置的开发人员客户端或允许成员添加自己的连接器的组织，请直接在您自己的客户端设置中添加端点。

### 克劳德个体 {#mcp-install-individual-claude}

对于单个计划中的`claude.ai`和[!DNL Claude]桌面：

1. 打开&#x200B;**设置** > **连接器**。
2. 选择&#x200B;**添加自定义连接器**。
3. 输入`https://cx-coworker-gateway.adobe.io/mcp`作为服务器URL。
4. 保存并启用连接器，然后在首次使用时完成Adobe登录流程。

### ChatGPT个人 {#mcp-install-individual-chatgpt}

1. 打开&#x200B;**设置** > **连接器**。 在某些计划中，它显示为&#x200B;**设置** > **应用和连接器**。
2. 选择&#x200B;**添加连接器**。
3. 输入`https://cx-coworker-gateway.adobe.io/mcp`作为服务器URL。
4. 保存并启用连接器，然后在首次使用时完成Adobe登录流程。

### 光标 {#mcp-install-individual-cursor}

1. 打开&#x200B;**设置** > **MCP**。
2. 选择&#x200B;**添加新服务器**。
3. 输入`https://cx-coworker-gateway.adobe.io/mcp`作为服务器URL。
4. 选择&#x200B;**连接**&#x200B;并完成Adobe登录流程。

连接后，在Cursor的Composer和Agent模式中提供了标题为Adobe for CX Co-worker Gateway的工具。

### Claude码 {#mcp-install-individual-claude-code}

从终端添加端点：

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

然后启动[!DNL Claude Code]并运行：

```text
/mcp
```

选择`cx-enterprise`服务器并在浏览器中完成Adobe登录流程。

### 法典 {#mcp-install-individual-codex}

从终端添加端点：

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

身份验证：

```bash
codex mcp login cx-enterprise
```

验证配置：

```bash
codex mcp list
```

您还可以将终结点直接添加到`~/.codex/config.toml`：

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### 常规JSON配置 {#mcp-install-individual-json}

对于接受基于JSON的MCP服务器配置的客户端，请根据您的客户端是支持本机远程HTTP还是需要本地网桥，使用以下格式之一。

**通过`mcp-remote`桥**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**本机远程HTTP**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### 其他客户端 {#mcp-install-individual-other}

对于支持远程MCP的其他桌面或Web客户端，请使用`https://cx-coworker-gateway.adobe.io/mcp`添加作为HTTP服务器的适用于CX协同工作网关的Adobe。 除非您的客户端需要占位符值，否则将可选标头、持有者令牌字段、客户端ID字段和客户端密钥字段保留为空。

## 工具调用的产品上下文 {#mcp-connect-params}

MCP将每个工具调用范围限定为一个活动的Adobe组织。 除此之外，上下文要求取决于产品：

- **基于Experience Platform的产品** — Real-Time CDP、Experience Platform和Journey Optimizer工具在Experience Platform沙盒中运行。 每个会话设置沙盒一次；所有三个会话都共享该沙盒。
- **其他产品** — 未在Experience Platform上构建的产品不使用沙盒上下文。 Adobe Analytics、Customer Journey Analytics、Workfront、Marketo和Target工具针对其各自的产品资源进行解析，例如Customer Journey Analytics的数据视图和Adobe Analytics的报表包。

在会话开始时设置一次上下文 — 单个产品工具在会话期间不会切换组织、沙盒或数据视图。 有关设置组织、沙盒和数据视图上下文的工具，请参阅[会话上下文工具](context-tools.md)。

示例：

> “在此会话中使用组织`1234ABCD@AdobeOrg`、沙盒`prod`和数据视图`My Company — Global`。”

如果您不知道所需的值，请让您的MCP客户端列出可用于您的Adobe凭据的组织、沙盒或数据视图。