---
solution: Real-Time Customer Data Platform
title: Real-Time CDP MCP (Beta)
description: 了解如何使用MCP服务器将Adobe Real-Time CDP连接到MCP客户端。
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="Beta 版" type="Informative"
role: User, Developer
level: Beginner, Intermediate
source-git-commit: b2c93fd31bb72ebaf79aaa07aab68d39e63dc9b5
workflow-type: tm+mt
source-wordcount: '2634'
ht-degree: 0%

---

# Real-Time CDP MCP (Beta) {#rtcdp-mcp}

您可以使用Adobe Real-Time CDP MCP集成通过纯语言提示查询受众、目标和激活运行状况，而无需编写API调用或导航产品屏幕。 此集成同时为Adobe Real-Time CDP和Adobe Real-Time CDP B2B edition客户提供服务，提供了一种对话式方式，以便从与MCP兼容的客户端检查支持的Real-Time CDP数据和工作流。 阅读本指南，了解集成的工作原理、您可以对其执行的操作以及如何入门。

>[!AVAILABILITY]
>
>Real-Time CDP MCP位于Beta中。 该功能和文档可能会发生更改。 Real-Time CDP MCP服务器作为&#x200B;**远程HTTP传输服务器**&#x200B;进行分发，用户可在支持的MCP客户端和应用程序平台（例如，[!DNL Claude]、[!DNL ChatGPT]、[!DNL Claude Code]、[!DNL Codex]、[!DNL Cursor]或[!DNL VS Code]）中安装和配置该服务器。 身份验证通过&#x200B;**基于浏览器的登录流程**&#x200B;来处理 — 当您的客户端首次连接到服务器时，它会打开您的默认浏览器，以便您可以使用您的Adobe凭据登录并授权访问。 请联系您的Adobe代表以访问此Beta计划。

## Beta、安全和法律声明 {#mcp-notices}

**Beta文档声明：**&#x200B;此文档涵盖了Beta的一项功能，并不构成最终文档。 此处描述的内容与Beta版本有关，在正式发布之前可能会发生更改。 Adobe不对本文档的完整性或准确性做出任何表示。

使用Adobe Real-Time CDP MCP Server (Beta) (“Beta”)，即表示您在此确认Beta按“原样”提供&#x200B;**，不提供任何形式的担保**。 Adobe没有义务维护、更正、更新、更改、修改或以其他方式支持Beta。 建议您谨慎使用，切勿依赖此类Beta和/或随附材料的正确功能或性能。 Beta被视为Adobe的机密信息。 您向Beta提供的任何“反馈”（有关Beta的信息，包括但不限于您在使用Adobe时遇到的问题或缺陷、建议、改进和推荐）均会分配给Adobe，其中包括针对该反馈的所有权利、标题和兴趣。

>[!WARNING]
>
>模型上下文协议(MCP)是一种新兴的开源标准，可能会带来安全性或可靠性风险。 Adobe MCP服务器集成和相关文档按“原样”提供，不提供任何类型的担保。
>
>将MCP客户端或服务器连接到Adobe产品是客户选择的配置。 客户负责评估任何MCP集成的安全性和适用性。 Adobe对于因错误配置、滥用MCP、第三方实施中的漏洞或通过支持MCP的工作流执行的意外操作而产生的问题，概不负责。
>
>为了降低风险，Adobe鼓励您在生产使用之前在沙盒环境中测试集成，并在确认或依赖集成之前，仔细审查和验证所有MCP启动的操作和响应。

## 什么是模型上下文协议？ {#mcp-overview}

营销、数据和客户体验团队日益依赖基于聊天的应用程序和开发人员工具（如Anthropic Claude、OpenAI ChatGPT、Cursor和Microsoft Copilot Studio）来简化日常工作。 这些应用程序支持&#x200B;**模型上下文协议(MCP)**，这是一个开放标准，允许应用程序以统一的方式向大型语言模型(LLM)公开后端工具。

Real-Time CDP现在提供了一个MCP服务器，可直接在任何MCP兼容的应用程序中呈现受众、目标和激活操作。 借助Real-Time CDP MCP集成，不同的角色可以围绕相同的分段和激活数据展开协作 — 无需针对Adobe Experience Platform REST API编写查询或导航多个UI屏幕。 客户可以通过对话方式描述其意图，并让LLM调用相应的MCP工具。

## 主要功能 {#mcp-capabilities}

Real-Time CDP MCP服务器是&#x200B;**只读**&#x200B;监视和分类表面。 它会在您的AI助手中公开跨受众、目标、源、身份和配置文件解析检索API，作为纯语言答案，而无需编写查询或导航产品屏幕。 不能通过MCP服务器创建、修改或删除任何数据。

>[!IMPORTANT]
>
>当前Beta中的所有工具均为&#x200B;**只读**。 不支持写入操作，包括创建、激活、更新或删除受众、目标或数据流。

Beta版本包括以下18种工具：

| 工具 | 描述 |
| --- | --- |
| `search_audiences` | 按名称、实体类型、生命周期状态、身份命名空间或来源列出和查找受众。 |
| `preview_audience_membership` | 在将PQL或SDD区段表达式另存为受众之前，估计其大小。 |
| `inspect_audience_evaluation_jobs` | 检索区段评估作业记录，以诊断批处理受众未刷新或确认最近评估历史记录的原因。 |
| `inspect_audience_export_jobs` | 检索受众导出作业记录，以确认导出已完成或显示失败详细信息。 |
| `search_destination_connectors` | 列出平台中可用的目标连接器类型（如[!DNL Amazon S3]、[!DNL Google Ads]、[!DNL Salesforce] CRM）。 |
| `search_destination_accounts` | 列出经过身份验证的目标帐户 — 目标连接器类型的已配置实例。 |
| `search_destination_input_connections` | 检索目标流的Experience Platform端输入 — 正在导出的受众或数据集。 |
| `search_destination_output_connections` | 检索目标流的外部端点 — 目标路径、文件格式和投放配置。 |
| `search_destination_flows` | 列出并检查已配置的目标激活流程，包括其状态、映射和计划。 |
| `inspect_flow_runs` | 检索源和目标流的执行历史记录 — 状态、计时、记录计数和每次运行的失败详细信息。 |
| `search_source_connectors` | 列出平台中可用的源连接器类型。 |
| `search_source_accounts` | 列出经过身份验证的源帐户 — 源连接器类型的已配置实例。 |
| `search_source_input_connections` | 检索源流的数据选择层 — 从帐户提取的内容。 |
| `search_source_output_connections` | 检索源流的Experience Platform数据集目标 — 所摄取的数据将登陆的位置。 |
| `search_source_flows` | 列出并检查配置的源摄取管道，包括其状态、映射和计划。 |
| `search_identity_namespaces` | 列出沙盒中的身份命名空间定义 — 包括Adobe标准命名空间和自定义命名空间。 |
| `search_merge_policies` | 列出合并策略记录，这些记录控制如何从配置文件片段中组合实时客户配置文件。 |
| `search_organizations` | 列出经过身份验证的用户可访问的Adobe组织。 |

## 用例 {#mcp-use-cases}

Real-Time CDP MCP服务器专为&#x200B;**监视和分类**&#x200B;而设计。 由于服务器使用ID而不是名称，因此典型的工作流以列表开头 — 让Claude向您显示可用的项目，选择所需的项目，然后使用它返回的ID提出后续问题。

| 目标 | 示例提示 |
| --- | --- |
| **列出您的受众** | “在`prod`沙盒中列出我的受众。” |
| **检查特定受众** | “显示受众ID `abc123`的详细信息和生命周期状态。” |
| **诊断评估失败** | “给我看最近的评估作业并标记任何失败。” |
| **检查导出作业** | “列出最近的受众导出作业，并向我显示每个作业的状态。” |
| **估算受众规模** | “在保存此PQL表达式之前，先估算其大小：`homeAddress.country = 'US'`。” |
| **列出目标连接器类型** | “我的沙盒中有哪些目标连接器类型？” |
| **列出配置的目标帐户** | “列出我的目标帐户及其连接状态。” |
| **列出目标流** | “列出我的目标激活流程，并显示哪些流程已启用或已禁用。” |
| **检查目标流** | “显示目标流ID `xyz789`的完整配置。” |
| **检查目标帐户运行状况** | “列出我的目标帐户，并标记任何处于错误状态的帐户。” |
| **监视最近的激活运行** | “向我显示过去24小时内的流量运行情况，并标记任何故障。” |
| **调查失败的运行** | “显示流ID `xyz789`的运行历史记录并总结所有错误。” |
| **列出源流** | “列出我的源摄取流并显示其当前状态。” |
| **检查源流** | “向我显示源流ID `src456`的配置 — 它摄取了哪些内容？它登陆到了哪里？” |
| **检查摄取运行状况** | “显示源流ID `src456`的最近运行历史记录并标记失败。” |
| **列出身份命名空间** | “我的沙盒中配置了哪些身份命名空间？” |
| **列出合并策略** | “列出我的合并策略并显示默认策略。” |
| **查找您的组织ID** | “列出我有权访问的Adobe组织。” |

## 访问和启用 {#mcp-access}

>[!AVAILABILITY]
>
>Real-Time CDP MCP服务器位于Beta中，未开放进行自助注册。 仅通过邀请访问，并且需要在连接之前明确Adobe您的列入允许列表组织。

要请求访问权限，请执行以下操作：

1. 请联系您的Adobe客户代表（客户成功经理、技术客户经理或客户经理），并表达您对Real-Time CDP MCP Beta计划的兴趣。
2. 您的Adobe代表将与产品团队协调以评估资格并启用您的组织ID。
3. 启用后，您的Adobe代表将确认访问并提供任何其他入门培训材料。

>[!NOTE]
>
>只有明确启用的组织才能连接到Real-Time CDP MCP服务器。 尝试在启用之前连接将导致身份验证错误。

## 先决条件 {#mcp-prerequisites}

在将Real-Time CDP MCP服务器连接到MCP客户端之前，请确保：

* 您拥有有效的Real-Time CDP许可证。
* 您的Adobe代表已为Beta计划启用Adobe组织（请参阅[访问和启用](#mcp-access)）。
* 您有权访问支持的MCP客户端，如[!DNL Claude]、[!DNL ChatGPT]、[!DNL Claude Code]、[!DNL Codex]、[!DNL Cursor]或[!DNL VS Code]。
* 您拥有组织ID以及要查询的沙盒的名称。
* 您在Adobe Experience Platform中拥有查看受众、目标和流服务实体的必要权限。

## 连接Real-Time CDP MCP服务器 {#mcp-connect}

Real-Time CDP MCP服务器端点为：

```
https://rtcdp-mcp.adobe.io/mcp
```

服务器使用&#x200B;**远程HTTP （可流式传输HTTP）传输**&#x200B;以及基于&#x200B;**浏览器的Adobe登录流程**。 在每个客户端中，安装模式都相同：

1. 添加服务器URL： `https://rtcdp-mcp.adobe.io/mcp`
2. 保存或启用连接。
3. 在客户端首次调用工具时完成&#x200B;**基于浏览器的Adobe登录**。
4. 在每个会话开始时提供`imsOrgId`和`sandboxName`。

### 常规JSON配置 {#mcp-connect-json}

对于接受基于JSON的MCP服务器配置的客户端(如Claude Desktop (`claude_desktop_config.json`)、VS Code或任何读取`mcp.json`文件的客户端)，请根据您的客户端是支持本机远程HTTP还是需要本地网桥，使用以下格式之一：

**通过`mcp-remote`桥（Claude Desktop和其他需要本地桥的客户端）**

```json
{
  "mcpServers": {
    "rtcdp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://rtcdp-mcp.adobe.io/mcp"
      ]
    }
  }
}
```

**本机远程HTTP （直接支持它的客户端）**

```json
{
  "mcpServers": {
    "rtcdp": {
      "url": "https://rtcdp-mcp.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

>[!NOTE]
>
>配置中不需要任何API密钥、持有者令牌或其他标头。 首次使用时，身份验证完全通过基于浏览器的Adobe登录流程进行处理。

### 在基于UI的客户端中安装 {#mcp-connect-ui}

#### 克劳德

对于`claude.ai`和Claude Desktop，使用服务器URL `https://rtcdp-mcp.adobe.io/mcp`将Real-Time CDP MCP服务器添加为&#x200B;**自定义连接器**。

* **单个计划** — 在Claude中，导航到&#x200B;**自定义→连接器**，选择&#x200B;**添加连接器**，然后输入服务器URL。
* **团队和企业计划** — 工作区&#x200B;**所有者**&#x200B;或&#x200B;**主要所有者**&#x200B;在&#x200B;**组织设置→连接器**&#x200B;下添加了连接器。 添加后，每个用户都会在自己的Claude设置中启用它。

添加连接器后，在对话中启用该连接器，并在首次使用时完成Adobe浏览器登录。 Claude自动发现Adobe授权服务器 — 不需要客户端ID或客户端密钥。

#### ChatGPT

在[!DNL ChatGPT]中，将Real-Time CDP MCP服务器添加为&#x200B;**自定义连接器**：

1. 导航到&#x200B;**设置→连接器**（或&#x200B;**设置→应用和连接器**，具体取决于您的计划）。
2. 选择&#x200B;**添加连接器**&#x200B;并输入`https://rtcdp-mcp.adobe.io/mcp`作为服务器URL。
3. 保存连接器。 根据您的[!DNL ChatGPT]计划，此步骤可能需要&#x200B;**开发人员模式**&#x200B;或工作区管理员批准。
4. 连接器启用后，在首次使用出现提示时，请通过Adobe浏览器登录进行身份验证。

#### 光标

在光标中，将Real-Time CDP MCP服务器添加为远程MCP服务器：

1. 打开&#x200B;**MCP**→设置。
2. 选择&#x200B;**添加新服务器**&#x200B;并输入`https://rtcdp-mcp.adobe.io/mcp`作为服务器URL。
3. 选择&#x200B;**connect**&#x200B;以触发基于浏览器的Adobe登录和身份验证。

连接后，Real-Time CDP工具在Cursor的“编辑器”和“代理”模式下可用。

#### 其他基于用户界面的客户端

对于客户端（如VS Code或其他支持远程MCP的桌面和Web应用程序），请使用`https://rtcdp-mcp.adobe.io/mcp`将Real-Time CDP MCP服务器添加为&#x200B;**远程HTTP**&#x200B;服务器。 如果客户端支持可选标头或持有者令牌，请将它们留空 — 身份验证在首次使用时通过基于浏览器的Adobe登录流处理。

### 在技术客户端中安装 {#mcp-connect-technical}

#### Claude码

从终端添加服务器：

```bash
claude mcp add --transport http rtcdp https://rtcdp-mcp.adobe.io/mcp
```

然后启动Claude Code并运行：

```text
/mcp
```

选择`rtcdp`服务器并在浏览器中完成Adobe登录流程。 如果您已在`claude.ai`中添加服务器，则当两者登录到同一帐户时，它可能会自动显示在Claude代码中。

#### 法典

从终端添加服务器：

```bash
codex mcp add rtcdp --url https://rtcdp-mcp.adobe.io/mcp
```

验证服务器：

```bash
codex mcp login rtcdp
```

验证配置：

```bash
codex mcp list
```

您还可以将服务器直接添加到`~/.codex/config.toml`：

```toml
[mcp_servers.rtcdp]
url = "https://rtcdp-mcp.adobe.io/mcp"
```

### 必需的请求参数 {#mcp-connect-params}

每个工具调用都需要两个参数，用于将请求范围限定到您的Adobe Experience Platform租户：

* `imsOrgId` — 您的组织ID，在下游Experience Platform API调用中映射到`x-gw-ims-org-id`标头。
* `sandboxName` — Experience Platform沙盒名称，已映射到`x-sandbox-name`标头。

在每个会话开始时提供这些参数。 例如：

> “在此会话中使用组织`1234ABCD@AdobeOrg`和沙盒`prod`。”

如果您不知道组织ID，请让您的AI助手调用`search_organizations` — 它将返回您的Adobe凭据可以访问的每个组织。

## 已知限制(Beta) {#mcp-limitations}

以下限制适用于[!DNL Adobe Real-Time CDP] MCP服务器的当前Beta版本：

| 限制 | 描述 | 解决方法 |
| --- | --- | --- |
| **只读表面** | MCP服务器仅公开检索API。 您无法创建、更新、激活或删除受众、目标或数据流。 | 使用Real-Time CDP UI或Experience Platform REST API执行写入操作。 |
| **没有参与或传递量度** | MCP服务器不会从目标平台返回下游投放统计信息、参与或转化量度。 | 使用目标平台自己的报表、Customer Journey Analytics MCP或Adobe Analytics MCP获取参与和转化数据。 |
| **区段查询必须在外部创作** | `Preview Audience Membership`需要有效的PQL或SDD表达式作为输入；MCP服务器不会为您撰写查询。 | 在区段生成器UI中或通过分段服务API创作PQL/SDD表达式，然后粘贴到MCP提示符下。 |
| **通过继续令牌分页** | 列表工具返回分页结果。 超大型沙盒中的完整枚举需要链接`continuationToken`调用。 | 使用过滤器（名称、状态、连接规范、时间范围）而不是枚举完整列表来缩小查询。 |
| **激活运行筛选仅基于时间** | `Inspect Activation Runs`支持按状态和完成时间戳（纪元毫秒UTC）进行筛选，但不支持直接按错误类型或目标平台进行筛选。 | 首先按`flowId`筛选（从`List Configured Destinations`获取），以将运行范围限定到特定目标。 |
| **会话开始时需要组织ID** | 每个工具调用（除`search_organizations`外）都需要`imsOrgId`和`sandboxName`作为显式参数。 如果未提供这些参数，则工具调用将失败。 | 在每个会话开始时，告诉您的AI助手：“将组织`<YOUR_ORG_ID>`和沙盒`<SANDBOX_NAME>`用于此会话。” 如果您不知道组织ID，请先调用`search_organizations` — 它将返回您的凭据可以访问的组织。 |

## 常见问题 {#mcp-faq}

+++支持哪些MCP客户端？

Real-Time CDP MCP服务器可与支持远程MCP服务器或自定义连接器的任何客户端配合使用 — 包括[!DNL Claude]、[!DNL ChatGPT]、[!DNL Claude Code]、[!DNL Codex]、[!DNL Cursor]和[!DNL VS Code]。 设置流程取决于客户端：基于UI的客户端通常从设置或连接器面板添加服务器，而技术客户端（如Claude Code和Codex）可以从命令行或配置文件添加服务器。
+++

+++如何获取访问权限？

只有在Beta期间受邀才能访问。 请联系您的Adobe客户代表（客户成功经理、技术客户经理或客户经理）以请求注册。 您的Adobe代表将与产品团队协调以启用您的组织。 有关详细信息，请参阅[访问和启用](#mcp-access)。
+++

+++身份验证如何工作？

身份验证是通过基于&#x200B;**浏览器的登录**&#x200B;处理的。 当MCP客户端首次调用某个工具时，它将打开默认浏览器以访问Adobe登录页面。 在对客户端进行身份验证和授权后，将会建立会话，后续工具调用会重复使用它。 您的客户端配置中无需存储API密钥或长效凭据。
+++

+++我可以通过MCP访问哪些Real-Time CDP对象？

您可以访问受众、目标类型、配置的目标帐户、目标数据流、源和目标连接以及激活运行历史记录。 操作是只读的（检索API）；当前版本不支持写入操作。
+++

+++要使用Real-Time CDP MCP服务器，是否需要开发人员访问权限？

不是。 MCP服务器专为营销和技术人员而设计。 营销人员可以在任何支持的MCP客户端中使用自然语言提示与其交互，而数据工程师和开发人员可以在支持MCP的开发人员工具中使用它。
+++

