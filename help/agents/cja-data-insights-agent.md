---
description: 了解如何使用Customer Journey Analytics中的Data Insights Agent可视化数据
title: 在Customer Journey Analytics中使用Data Insights Agent可视化数据
role: User, Admin
solution: Customer Journey Analytics
source-git-commit: 04a73ac0f705cd3a2184fb2f8599aff85b7bb5e5
workflow-type: tm+mt
source-wordcount: '2499'
ht-degree: 1%

---

# 使用Data Insights Agent可视化数据

>[!AVAILABILITY]
>
>Data Insights Agent在有限的时间内向符合条件的客户提供。 Data Insights Agent的访问截止日期为2026年2月28日。 要继续使用Data Insights Agent而不中断，请联系您的Adobe客户代表以了解有关许可Adobe Experience Platform Agent Orchestrator的更多信息。

Data Insights Agent可从Customer Journey Analytics中的[AI Assistant](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/ai-assistant)访问，它是一个创作AI对话代理，可快速高效地回答有关您数据的问题。 它使用数据视图中的组件并使用实际数据在Analysis Workspace中构建相关可视化图表。

使用Data Insights Agent在Analysis Workspace中解答以数据为中心的问题，可以节省您原本要在Analysis Workspace中手动构建可视化并熟悉数据视图组件所花费的无数时间。

AI助手中的![Data Insights Agent](images/cja-agent//cja-ai-asst-da.gif)

## 范围内功能与范围外功能

| 功能 | 范围 | 超出范围 |
| --- | --- | --- |
| **可视化类型** | <ul><li>线形图</li><li>多行</li><li>自由格式表</li><li>条形图</li><li>圆环图</li><li>摘要数字</li></ul> | <ul><li>流量</li><li>流失</li><li>同类群组表</li><li>面积图，栈叠的面积图</li><li>栈叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图、栈叠的水平条形图</li><li>关键量度摘要</li><li>散点图</li><li>概要变化</li><li>文本</li><li>树状图</li><li>维恩图</li><li>指导分析：主动增长、转化趋势、参与度、首次使用影响、频度、Funnel、净增长、发布影响、保留、时间线、趋势</li></ul> |
| **Workspace操作和代理功能** | <ul><li>构建和更新可视化图表<p>生成自由格式表和相关的可视化图表（例如折线图、条形图、圆环图等）。<p>例如，*从2月到5月，跨SKU的利润是多少？*</p></li><li>提出跟进问题<p>响应上下文中的任何先前提示中的提示。 例如：</p> <ul><li>提示1：*从3月开始的趋势事件。*</li><li>提示2： *改为向我显示从3月到4月的数据*</li></ul> </li><li>范围外提示检测<p>如果您提交了一个超出范围的提示，如&#x200B;*导出此项目*，Data Insights Agent会通知您问题超出范围，从而做出响应。</p></li></ul> | <ul><li>共享</li><li>导出</li><li>下载</li><li>管理用户首选项</li><li>管理数据视图</li><li>Analytics功能板应用程序</li><li>归因</li><li>内联摘要或响应<p>Data Insights Agent无法在聊天边栏中以用户提示的摘要答案进行内联响应。 范围外提示的示例包括：*给我上一个提示的见解摘要*&#x200B;和&#x200B;*总结折线图可视化图表的亮点。*</p></li></ul> |
| **澄清问题** | 如果您提的问题没有足够上下文可供Data Insights Agent回答，或者过于宽泛，Data Insights Agent会用一个澄清问题或建议的选项进行响应。 <p>以下澄清性问题是组件相关问题的示例：</p><ul><li>量度：*您指的是哪个“收入”量度？*</li><li>Dimension：*您想关注以下“地区”中的哪一个？*</li><li>区段： *您要应用哪个“帐户”区段？*</li><li>日期范围： *对于“上个月”，您是指“上个月”还是“最近30天”？*</li></ul><p>以下澄清问题是与维度项目相关的一个问题的示例：</p> <ul><li>你是指哪个“商店名称”？ (例如，存储#5274、存储#2949等。)</li></ul> | 澄清问题仅限于组件和维度项目。 Data Insights Agent无法阐明数据视图、可视化图表、数据粒度、比较和范围等内容。 当澄清无法使用的问题时，代理将默认使用您最可能要求的内容。 如果它返回意外的可视化图表或数据粒度，您可以提出后续问题或调整可视化图表和数据。 |
| **数据可验证性和正确性** | 通过查看生成的自由格式表和数据可视化图表，可以确认数据的可验证性和正确性。 <p>例如，如果您要求Data Insights Agent显示上个月&#x200B;*的*&#x200B;趋势订单，则可以确认在新生成的面板、数据可视化图表和自由格式表中选择了正确的指标（“订单”）和日期范围（“上个月”）。 | Data Insights Agent不会通过通知您添加了哪些组件或可视化图表来进行响应。</p> |
| **反馈机制** | <ul><li>竖起大拇指</li><li>拇指朝下</li><li>标记</li></ul> |  |


## 管理对Data Insights Agent的访问 {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="为Data Insights Agent启用"
>abstract="此选项启用此数据视图，以便与Data Insights Agent一起使用。 Data Insights Agent是一个可从Customer Journey Analytics中的AI助手访问的创作AI会话代理。 它有助于您通过文本提示快速分析数据。 它使用数据视图中的组件并使用实际数据在Analysis Workspace中构建相关可视化图表。"

<!-- markdownlint-enable MD034 -->

以下参数可管理对Customer Journey Analytics中Data Insights Agent的访问：

* **解决方案访问**：在2025年11月30日之前，所有Customer Journey Analytics客户都可将Data Insights Agent作为有限访问计划的一部分使用。 在Adobe Analytics中不可用。

* **合同访问权限**：如果您无法在AI助手中使用Data Insights Agent，请联系贵组织的管理员或Adobe帐户团队。 在贵组织可以使用Data Insights Agent之前，您必须同意与创作AI相关的某些法律条款。

* **权限**：必须先在[!UICONTROL Adobe Admin Console]中授予必要的权限，用户才能访问Data Insights Agent。

  要授予权限，[产品配置文件管理员](https://helpx.adobe.com/enterprise/using/manage-product-profiles.html)必须在[!UICONTROL Admin Console]中完成以下步骤：

   1. 在&#x200B;**[!UICONTROL Admin Console]**&#x200B;中，选择&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡以查看&#x200B;**[!UICONTROL 所有产品和服务]**&#x200B;页面。
   1. 选择&#x200B;**[!UICONTROL Customer Journey Analytics]**。
   1. 在&#x200B;**[!UICONTROL 产品配置文件]**&#x200B;选项卡上，选择要为其提供[!UICONTROL AI助手：产品知识]访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。

      Admin Console中的![权限选项卡](images/cja-agent/ai-assistant-permissions-tab.png)

   1. 在提供的表中的&#x200B;**[!UICONTROL 报告工具]**&#x200B;行中，选择编辑图标![编辑](images/cja-agent/Edit.svg)。
   1. 滚动到或搜索&#x200B;**[!UICONTROL AI助手：产品知识]**，然后选择此权限旁边的加号图标![AddCircle](images/cja-agent/AddCircle.svg)。
   1. 滚动到或搜索&#x200B;**[!UICONTROL Data Insights Agent]**，然后选择此权限旁边的加号图标![AddCircle](images/cja-agent/AddCircle.svg)。

      **[!UICONTROL AI助手：产品知识]**&#x200B;权限和&#x200B;**[!UICONTROL Data Insights Agent]**&#x200B;权限已添加到&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;列。

      ![添加权限](images/cja-agent/ai-assistant-permissions.png)。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

  有关访问控制的详细信息，请参阅[访问控制](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/access-control#access-control)。

* **数据视图访问**：必须为Data Insights Agent启用数据视图。

  >[!IMPORTANT]
  >
  >启用数据视图时，请考虑以下事项：
  >* 每个IMS组织最多可启用50个数据视图。 如果您在给定组织的所有产品配置文件中启用了超过50个数据视图，Data Insights Agent将使用50个最常用的数据视图。
  >* 在启用数据视图的同一天，Data Insights Agent可以引用包含的数据视图。

  要为Data Insights Agent启用数据视图，请执行以下操作：

   1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。
   1. 选择要为Data Insights Agent启用的一个或多个数据视图，然后选择&#x200B;**[!UICONTROL 为Data Insights Agent启用]**。

      ![启用Data Insights Agent的数据视图](images/cja-agent/data-view-enable-dia.png)

  要查看在IMS组织中为Data Insights Agent启用的数据视图的数量，请执行以下操作：

   1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。
   1. 选择&#x200B;**[!UICONTROL Data Insights Agent]**&#x200B;列顶部的信息图标。

      ![Data Insights Agent信息图标](images/cja-agent/data-insights-agent-tooltip.png)

## 在AI助手中访问Data Insights Agent

1. 转到[experience.adobe.com](https://experience.adobe.com/)并使用Adobe ID登录。
1. 从Experience Cloud主页中选择&#x200B;**Customer Journey Analytics**。
1. 在项目页面顶部的横幅中选择&#x200B;**[!UICONTROL 空白项目]**&#x200B;以打开一个新的空白项目。
1. 请确保为面板选择的数据视图是已启用与Data Insights Agent一起使用的数据视图，如[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)中所述。
1. 选择页面右上角的AI Assistant聊天图标。

   如果您看不到聊天图标，请联系您的管理员，以便管理员在Admin Console中启用以下功能：

   * 报告工具： **[!UICONTROL AI助手：产品知识]**
   * 数据视图工具： **[!UICONTROL Data Insights Agent]**

   有关其他详细信息，请参阅[在Customer Journey Analytics中管理对Data Insights Agent的访问](#manage-access-to-data-insights-agent-in-customer-journey-analytics)。

   ![AI助手图标](images/cja-agent/ai-asst-icon.png)

1. 在页面底部的&#x200B;**[!UICONTROL 关于Customer Journey Analytics]**&#x200B;对话框中，使用Data Insights Agent提出数据可视化问题。

   有关更多信息，请参阅以下示例。

### 示例 1

例如，假设您对您的企业在7月份收到的订单感兴趣。

**提示：**&#x200B;输入&#x200B;*“7月份的趋势订单”。*

![AI提示](images/cja-agent/ai-asst-prompt1.png)

**响应：** Data Insights Agent通过查看数据视图中的数据（包括量度和组件）来收集见解。 它会将提示转换为数据范围内正确的维度和量度。

如您所见，它会自动生成一个线形图和一个自由格式表来显示7月的订单。

![提示答案 — 折线图和自由格式表](images/cja-agent/ai-asst-result.png)

### 示例 2

接下来，您需要查看收入在不同地区的比较情况。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按地区显示收入”*。

**响应：** Data Insights Agent智能地理解了“地区”的意思，即“客户地区”。 该报表会生成一个条形图，其中按地区显示收入的情况最好：

![条形图](images/cja-agent/ai-asst-result2.png)

### 示例3

接下来，除了按地区了解收入之外，您还需要按地区查看利润数据。 您可以要求Data Insights Agent更新最新的可视化图表和自由格式表，而不是重复之前的提示。

**提示：**&#x200B;在提示窗口中，键入&#x200B;*“添加利润”*。

**响应：** **[!UICONTROL 条形]**&#x200B;图表仍提供最简洁的答案，但利润指标已添加为自由格式表中的列：

![条形图](images/cja-agent/ai-asst-result4.png)

### 示例4

最后，我们来了解一下按产品类别划分的收入。

**提示：**&#x200B;在提示窗口中，输入&#x200B;*“按产品类别列出的收入比例”。*

**响应：**&#x200B;同样，Data Insights Agent选择最合适的可视化图表（在本例中为&#x200B;**[!UICONTROL 圆环图]**&#x200B;可视化图表）来回答问题。

![圆环图](images/cja-agent/ai-asst-result3.png)

## 跨Experience Cloud应用程序访问Data Insights Agent

Adobe Experience Platform Agent Orchestrator允许您在多个Adobe Experience Cloud应用程序(如Data Insights Agent和Real-Time CDP)中访问Adobe Journey Optimizer的功能。

Agent Orchestrator解释您的请求，确定需要哪些专业代理，并协调他们提供正确的响应。 它可以跨多轮交互跟踪上下文，因此您可以自然地基于先前的查询进行构建。

有关详细信息，请参阅[Adobe Experience Platform Agent Orchestrator](/help/agents/agent-orchestrator.md)。

## 示例数据可视化提示

以下是常见提示的一些示例以及Data Insights Agent用于响应这些提示的可视化图表。

| 示例提示 | 预期可视化图表 |
| --- | --- |
| 显示[个月]的利润 | 线形图<p>默认情况下，在特定时间范围内请求趋势或量度会返回折线图可视化图表。 |
| [月]的订单趋势 | 线形图 |
| 在[月]内按地区显示收入 | 条形图 |
| 按产品类别分列的收入份额 | 圆环图 |
| 按星期几的订单，从1月到5月 | 条形图 |
| 按性别显示从3月到6月的订单 | 条形图 |
| 从2月到5月，跨SKU的利润如何 | 条形图 |
| [月]内按商店名称列出的收入 | 条形图 |
| 按[月]的利润计算，我的前10个SKU是什么？ | 条形图 |
| 按月份划分的购买比例 | 圆环图 |
| [个月]的总利润 | 摘要数字<p>如果要求提供特定时间范围内的量度“总计”，应当会返回“摘要数字”可视化图表。 |

## 提示最佳实践

Data Insights Agent会处理每个用户提示提供的上下文，并尝试以自由格式表形式智能地响应最合适的可视化和组件。

响应可能会因提示中使用的具体字词和短语而异，语言的细微变化可能会导致不同的结果。

要获得最佳结果，请考虑以下准则：

* **具体：**&#x200B;包含精确术语以缩小响应范围。 以下是一个特定提示示例：“上月在加利福尼亚的销售额”

* **使用清晰的量度、维度和区段：**&#x200B;添加特定的量度（如“收入”）、维度（如“网站名称”）、区段(如“iPhone用户”)和日期范围（如“过去三个月”）有助于Data Insights Agent关注正确的数据。

* **直接提问：**&#x200B;使用措辞提问可让Data Insights Agent更轻松地提供清晰、相关的见解。 下面是一个在提示中直接提出问题的示例：“按产品类别列出的今年平均收入是多少？”

请查看下表，了解可在Data Insights Agent的提示中使用的示例术语和短语，以及可期待的响应类型。

这些示例旨在帮助您了解特定字词或结构如何影响Data Insight Agent的输出，从而确保更精确、更有价值的洞察。 Data Insights Agent使用创作AI，因此可视化图表或选定的数据可能会在类似提示中略有不同。

| 预期结果 | 术语和短语示例 |
| --- | --- |
| 概要数字可视化 | <ul><li>总计</li></ul> |
| 比较组件 | <ul><li>比较</li><li>对比</li><li>对比度</li><li>每周</li><li>月同比</li><li>季度环比</li><li>年份</li></ul> |
| 圆环图可视化图表 | <ul><li>比例</li><li>共享</li><li>分发</li><li>百分比</li><li>贡献</li><li>部分</li><li>部分</li></ul> |
| 折线图可视化图表 | <ul><li>趋势</li><li>在[时间范围]内的[指标]</li></ul> |
| 条形图可视化 | <ul><li>[Dimension]的[指标]</li></ul> |

<!--

## Beta testing expectations and requested feedback

After posing each question, carefully review the assistant's provided answer. It's crucial to evaluate the generated visualizations comprehensively before providing feedback. 

Consider the following when evaluating a response from Data Insights Agent: 

* Chat rail response or template: Evaluate the textual response provided. Is the response appropriate given the context of your prompt? 

* Visualization/chart: Evaluate the visualization. Is it the appropriate or expected visualization for your question, or would you have expected a different visualization?  

* Freeform table: Evaluate the freeform table. Is the freeform table data correct? Is it breaking down data where requested? Are the applied segments those that you requested or expected? 

* Error Message / Out-of-Scope: If a generic error message is given stating the question is out of scope, provide feedback on whether you think the out-of-scope message is appropriate, given your prompt. Was your prompt actually in scope? 

**For every response, give a thumbs up or thumbs down, based on the response.**

Following the thumbs up or thumbs down selection, please make a selection for the relevant multi-select feedback boxes. If you want to provide additional feedback, add notes in the open text box.

## Questions and Contact

* Send questions and feedback in the Beta Slack channel: #data-insights-agent-in-cja-beta

-->


## 配置最佳实践

以下是您的Customer Journey Analytics配置（数据视图、计算量度、区段等）的最佳实践，以确保Data Insights Agent能够找到正确的组件并返回更干净的答案，而无需提示您输入其他信息。

* **平衡您需要的组件**。 请勿将数据集的所有字段作为量度或维度组件添加到数据视图。 特别是那些您绝不会在分析中使用的变量。 另一方面，不要严格限制自己只能使用预计分析所需的字段。 数据视图过于有限，限制了分析和Data Insights Agent功能的灵活性。
* **始终使用友好的显示名称**。 确保您在数据视图中定义的所有字段（作为量度或维度组件）都具有友好的组件名称。 使用友好名称重命名字段的过程与来自Adobe Analytics源连接器数据集的字段特别相关。 这些字段通常具有不友好的不可识别名称，如`eVar41`或`prop25`。
* **使用特殊名称**。 当您在数据视图中将同一字段用作量度和维度组件时，独特名称特别相关。 或者，当您在同一类型的多个组件（例如，在两个不同的量度中）中使用字段时，每个组件都具有不同的组件设置。
* **使用组件命名约定**。 您可以使用组件命名惯例对组件进行分组。 例如，**[!UICONTROL 订单 | 产品]**&#x200B;和&#x200B;**[!UICONTROL 订单 | 客户]**&#x200B;可以区分数据中可能存在的不同订单量度。
* **使用数据字典**。 在数据字典中添加组件的描述和其他相关数据。 数据Insight代理当前不使用数据字典中的描述和标记，但将来可能会使用。
* **使用批准的计算指标**。 同意一个流程，仅将批准的计算指标用作数据视图中的组件，并避免使用实验性的计算指标。
* **共享所需的区段**。 确保共享区段并显示Data Insights Agent提示所需的区段。
* **跨数据视图标准化组件名称**。 如果在多个数据视图中使用与组件相同的字段，请确保为该组件使用单个友好名称和单个标识符。 通过单个名称和标识符，Data Insights Agent可以切换数据视图而不会丢失上下文。

>[!MORELIKETHIS]
>
>[组件设置](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/overview)
>[数据字典](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/data-dictionary/data-dictionary-overview)
>[批准计算量度](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-approving)
>[共享区段](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-components/segments/seg-share)
