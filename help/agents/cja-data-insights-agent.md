---
description: 了解如何使用Customer Journey Analytics中的Data Insights Agent可视化数据
title: 在Customer Journey Analytics中使用Data Insights Agent可视化数据
role: User, Admin
solution: Customer Journey Analytics
TQID: https://experienceleague.adobe.com/UtKIDlN2x7MOAiHNRRQ8b5OO4fIwzV74r1fnfMwblcQ
product_v2:
  - id: e98b7246-966c-4318-9e95-cad2f7a17dc7
feature_v2:
  - id: b743a5d9-dc51-41ed-8b2f-86a1f8de430f
  - id: c73c4213-d623-4126-81f4-80b42e5e2656
  - id: ce577701-5b9e-4fe4-8fa3-4eedea976da4
subfeature_v2:
  - id: b1f5d324-a668-4e51-a59b-6fc0862d7310
  - id: bc7a5a86-1a70-451f-985c-037b65f091d1
  - id: df7fb1db-aa1b-4314-98ac-59dbfcc3044f
  - id: e44e560d-5e5c-4a5f-9a87-eb8adbb817af
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 2690
ht-degree: 4%

---

# 使用Data Insights Agent可视化数据

>[!AVAILABILITY]
>
>Data Insights Agent在有限的时间内向符合条件的客户提供。 Data Insights Agent的访问截止日期为2026年3月31日。 要在此日期之后继续使用Data Insights Agent而不中断，请联系您的Adobe客户代表以了解有关许可Adobe Experience Platform Agent Orchestrator的更多信息。

可从[AI Assistant](/help/ai-assistant/ai-assistant-ui.md)访问的Data Insights Agent是一个创作AI对话代理，可快速高效地回答有关您数据的问题。 它使用来自您的数据视图和实际数据的组件在Analysis Workspace中构建相关可视化图表。

使用Data Insights Agent在Analysis Workspace中回答以数据为中心的问题可以节省大量时间，否则，您可能要在Analysis Workspace中手动构建可视化并熟悉数据视图组件时会花费这些时间。

AI助手中的![Data Insights Agent](/help/agents/images/cja-agent/cja-ai-asst-da.gif)

## 范围内功能与范围外功能

| 功能 | 范围 | 超出范围 |
| --- | --- | --- |
| **可视化类型** | <ul><li>线形图</li><li>多行</li><li>自由格式表</li><li>条形图</li><li>圆环图</li><li>摘要数字</li></ul> | <ul><li>流</li><li>流失</li><li>同类群组表</li><li>面积图，栈叠的面积图</li><li>栈叠的条形图</li><li>项目符号</li><li>组合</li><li>直方图</li><li>水平条形图、栈叠的水平条形图</li><li>关键量度摘要</li><li>散点图</li><li>概要变化</li><li>文本</li><li>树状图</li><li>维恩图</li><li>指导分析：主动增长、转化趋势、参与度、首次使用影响、频度、Funnel、净增长、发布影响、保留、时间线、趋势</li></ul> |
| **Workspace操作和代理功能** | <ul><li>构建和更新可视化图表<p>生成自由格式表和相关的可视化图表（例如折线图、条形图、圆环图等）。</p><p>例如，*从2月到5月，跨SKU的利润是多少？*</p></li><li>提出跟进问题<p>响应上下文中的任何先前提示中的提示。 例如：</p> <ul><li>提示1：*从3月开始的趋势事件。*</li><li>提示2： *改为向我显示从3月到4月的数据*</li></ul> </li><li>范围外提示检测<p>如果您提交了一个超出范围的提示，如&#x200B;*导出此项目*，Data Insights Agent会通知您问题超出范围，从而做出响应。</p></li></ul> | <ul><li>共享</li><li>导出</li><li>下载</li><li>管理用户首选项</li><li>管理数据视图</li><li>Analytics功能板应用程序</li><li>归因</li><li>内联摘要或响应<p>Data Insights Agent无法在聊天边栏中以用户提示的摘要答案进行内联响应。 范围外提示的示例包括：*给我上一个提示的见解摘要*&#x200B;和&#x200B;*总结折线图可视化图表的亮点。*</p></li></ul> |
| **澄清问题** | 如果您提的问题没有足够上下文可供Data Insights Agent回答，或者过于宽泛，Data Insights Agent会用一个澄清问题或建议的选项进行响应。 <p>以下澄清性问题是组件相关问题的示例：</p><ul><li>量度：*您指的是哪个“收入”量度？*</li><li>Dimension: *Which of the below &quot;regions&quot; do you want to focus on?*</li><li>Segment: *Which &quot;Account&quot; segment did you want to apply?*</li><li>Date Range: *By &quot;last month,&quot; did you mean the last full month or the last 30 days?*</li></ul><p>The following clarifying question is an example of a question related to dimension items:</p> <ul><li>Which &quot;store name&quot; did you mean? (For example, Store #5274, Store #2949, and so forth.)</li></ul> | Clarifying questions are limited to components and dimension items. Data Insights Agent cannot clarify things such as data views, visualizations, data granularity, comparison, and scope. When clarifying questions cannot be used, the agent defaults to what you are most likely asking for. If it returns an unexpected visualization or data granularity, you can ask a follow-up question or adjust the visualization and data. |
| **Data verifiability and correctness** | Data verifiability and correctness can be confirmed by viewing the generated freeform table and data visualization. <p>For example, if you ask Data Insights Agent to *Trend orders last month*, you can confirm that the correct metric (&quot;orders&quot;) and date range (&quot;last month&quot;) were selected in the newly generated panel, data visualization, and freeform table.</p> | Data Insights Agent does not respond by informing you which components or visualizations were added. |
| **Feedback mechanisms** | <ul><li>Thumbs up</li><li>Thumbs down</li><li>标记</li></ul> |  |


## 管理对 Data Insights 代理的访问权限 {#manage-access}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="cja-enable-data-insights-data-view"
>title="为 Data Insights 代理启用"
>abstract="此选项可启用与 Data Insights 代理一起使用的数据视图。 Data Insights 代理是一个生成式 AI 对话代理，可以从 Customer Journey Analytics 中的 AI 助手访问。 它可帮助您通过文本提示词快速分析数据。 它使用来自数据视图的组件和您的实际数据在 Analysis Workspace 中构建相关的可视化图表。"

<!-- markdownlint-enable MD034 -->

The following parameters govern access to Data Insights Agent in Customer Journey Analytics:

* **Solution access**: Data Insights Agent is available for eligible customers for a limited time. Access to Data Insights Agent is available through February 28, 2026. It is not available in Adobe Analytics.

* **Contractual access**: If you are not able to use Data Insights Agent in the AI Assistant, please contact your organization&#39;s administrator or Adobe account team. Before your organization can use Data Insights Agent, you must agree to certain legal terms related to generative AI.

* **Permissions**: Necessary permissions must be granted in the [!UICONTROL Adobe Admin Console] before users can access Data Insights Agent.

  To grant permissions, a [product profile administrator](https://helpx.adobe.com/cn/enterprise/using/manage-product-profiles.html) must complete the following steps in the [!UICONTROL Admin Console]:
   1. 在&#x200B;**[!UICONTROL Admin Console]**&#x200B;中，选择&#x200B;**[!UICONTROL 产品]**&#x200B;选项卡以查看&#x200B;**[!UICONTROL 所有产品和服务]**&#x200B;页面。
   1. 选择&#x200B;**[!UICONTROL Customer Journey Analytics]**。
   1. 在&#x200B;**[!UICONTROL 产品配置文件]**&#x200B;选项卡上，选择要为其提供[!UICONTROL AI助手：产品知识]访问权限的产品配置文件的标题。
   1. 在特定产品配置文件中，选择&#x200B;**[!UICONTROL 权限]**&#x200B;选项卡。

      Admin Console中的![权限选项卡](/help/agents/images/cja-agent/ai-assistant-permissions-tab.png)

   1. 在提供的表中的&#x200B;**[!UICONTROL 报告工具]**&#x200B;行中，选择编辑图标![编辑](/help/agents/images/cja-agent/Edit.svg)。
   1. 滚动到或搜索&#x200B;**[!UICONTROL AI助手：产品知识]**，然后选择此权限旁边的加号图标![AddCircle](/help/agents/images/cja-agent/AddCircle.svg)。
   1. 滚动到或搜索&#x200B;**[!UICONTROL Data Insights Agent]**，然后选择此权限旁边的加号图标![AddCircle](/help/agents/images/cja-agent/AddCircle.svg)。

      **[!UICONTROL AI助手：产品知识]**&#x200B;权限和&#x200B;**[!UICONTROL Data Insights Agent]**&#x200B;权限已添加到&#x200B;**[!UICONTROL 包含的权限项]**&#x200B;列。

      ![添加权限](/help/agents/images/cja-agent/ai-assistant-permissions.png)。

   1. 选择&#x200B;**[!UICONTROL 保存]**&#x200B;以保存权限。

  有关访问控制的详细信息，请参阅[访问控制](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/technotes/access-control#access-control)。

* **数据视图访问**：必须为Data Insights Agent启用数据视图。

  >[!IMPORTANT]
  >
  >启用数据视图时，请考虑以下事项：
  >* 每个IMS组织最多可启用50个数据视图。 如果您在给定组织的所有产品配置文件中启用了超过50个数据视图，Data Insights Agent将使用50个最常用的数据视图。
  >  您可以使用数据视图[&#128279;](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/manage-dataviews#manage-data-views)中Data Insights Agent列上的信息查看IMS组织中为Data Insights Agent启用的数据视图数量。
  >* 在启用数据视图的同一天，Data Insights Agent可以引用包含的数据视图。

  要为Data Insights Agent启用数据视图，请执行以下操作：

   1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。

   1. 选择要为Data Insights Agent启用的一个或多个数据视图，然后选择&#x200B;**[!UICONTROL 为Data Insights Agent启用]**。

      ![启用Data Insights Agent的数据视图](/help/agents/images/cja-agent/data-view-enable-dia.png)

      有关为Data Insights Agent启用数据视图的详细信息，请参阅数据视图的[AI设置](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/create-dataview#ai-settings/help/data-views/create-dataview.md网站#ai-settings)。

  要查看在IMS组织中为Data Insights Agent启用的数据视图的数量，请执行以下操作：

   1. 在Customer Journey Analytics中，选择&#x200B;**[!UICONTROL 数据管理]** > **[!UICONTROL 数据视图]**。

   1. Select the info icon at the top of the **[!UICONTROL Data Insights Agent]** column.

      ![Data Insights Agent info icon](/help/agents/images/cja-agent/data-insights-agent-tooltip.png)


## Access Data Insights Agent in the AI Assistant

1. Go to [experience.adobe.com](https://experience.adobe.com/) and log in with your Adobe ID.

2. Select **Customer Journey Analytics** from Experience Cloud Home.

3. Select **[!UICONTROL Blank project]** in the banner at the top of the projects page to open a new blank project.

4. Ensure that the selected data view for the panel is a data view that was enabled for use with Data Insights Agent, as described in [Manage access to Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

5. Select the AI Assistant chat icon at the top-right area of the page.

   If you do not see the chat icon, contact your administrator so they can enable the following features in the Admin Console:

   * Reporting Tools: **[!UICONTROL AI Assistant: Product Knowledge]**

   * Data View Tools: **[!UICONTROL Data Insights Agent]**

   For additional details, see [Manage access to Data Insights Agent in Customer Journey Analytics](#manage-access-to-data-insights-agent-in-customer-journey-analytics).

   ![AI助手图标](/help/agents/images/cja-agent/ai-asst-icon.png)

6. In the **[!UICONTROL Ask about Customer Journey Analytics]** dialog at the bottom of the page, ask a data visualization question using Data Insights Agent.

   For more information, see the following examples.

### 示例 1

For example, let&#39;s say you are interested in the orders your business received in July.

**Prompt:** Enter *&quot;Trend orders in July.&quot;*

![AI prompt](/help/agents/images/cja-agent/ai-asst-prompt1.png)

**Response:** Data Insights Agent gathers insights by looking through the data in the data view, including the metrics and components. It translates the prompt into the right dimensions and metrics within the data range.

As you can see, it automatically generated a line graph and a freeform table to show orders for July.

![Answer to prompt - line graph and freeform table](/help/agents/images/cja-agent/ai-asst-result.png)

### 示例 2

Next, you want to see how your revenue compares by region.

**Prompt:** In the prompt window, enter *&quot;Show revenue by region.&quot;*

**Response:** Data Insights Agent intelligently understands that by &quot;region,&quot; you mean &quot;customer region.&quot; It produces a bar chart that best shows revenue by region:

![Bar chart](/help/agents/images/cja-agent/ai-asst-result2.png)

### Example 3

Next, in addition to understanding revenue by region, you also want to see data for profit by region. Instead of repeating the previous prompt, you can ask Data Insights Agent to update the most recent visualization and freeform table.

**Prompt:** In the prompt window, type *&quot;Add profit.&quot;*

**Response:** The **[!UICONTROL Bar]** chart still provides the most concise answer, but the profit metric has been added as a column in the freeform table:

![Bar chart](/help/agents/images/cja-agent/ai-asst-result4.png)

### Example 4

Finally, let&#39;s look at the revenue by product category.

**Prompt:** In the prompt window, enter *&quot;Proportion of revenue by product category.&quot;*

**Response:** Again, Data Insights Agent picks the most appropriate visualization, in this case the **[!UICONTROL Donut]** visualization, to answer the question.

![圆环图](/help/agents/images/cja-agent/ai-asst-result3.png)

## Access Data Insights Agent across Experience Cloud applications

Adobe Experience Platform Agent Orchestrator allows you to access the functionality of Data Insights Agent in multiple Adobe Experience Cloud applications, such as Adobe Journey Optimizer and Real-Time CDP.

Agent Orchestrator interprets your request, determines which specialized agents are needed, and orchestrates them to deliver the right response. It keeps track of context across multi-turn interactions, so you can build on prior queries naturally.

For more information, see [Adobe Experience Platform Agent Orchestrator](https://business.adobe.com/cn/products/experience-platform/agent-orchestrator.html).

## Example data visualization prompts

The following are some examples of common prompts and the visualizations used by Data Insights Agent to respond to those prompts.

| 示例提示 | Expected visualization |
| --- | --- |
| Show me profits in [Month] | 线形图<p>Asking for a trend or metric within a certain time range by default returns a line visualization. |
| Trend orders in [Month] | 线形图 |
| Show revenue by region in [Month] | 条形图 |
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

* **使用清晰的量度、维度和区段：**&#x200B;添加特定的量度（如“收入”）、维度（如“网站名称”）、区段（如“iPhone用户”）和日期范围（如“过去三个月”）有助于Data Insights Agent关注正确的数据。

* **直接提问：**&#x200B;使用措辞提问可让Data Insights Agent更轻松地提供清晰、相关的见解。 下面是一个在提示中直接提出问题的示例：“按产品类别列出的今年平均收入是多少？”

请查看下表，了解可在Data Insights Agent的提示中使用的示例术语和短语，以及可期待的响应类型。

这些示例旨在帮助您了解特定字词或结构如何影响Data Insights Agent的输出，从而确保更精确、更有价值的见解。 Data Insights Agent使用创作AI，因此可视化图表或选定的数据可能会在类似提示中略有不同。

| 预期结果 | 术语和短语示例 |
| --- | --- |
| 概要数字可视化 | <ul><li>合计</li></ul> |
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

* **平衡您需要的组件**。 请勿将数据集的所有字段作为量度或维度组件添加到数据视图，尤其是您不希望在分析中使用的那些字段。 另一方面，不要严格限制自己只能使用预计分析所需的字段。 数据视图过于有限，限制了分析和Data Insights Agent功能的灵活性。
* **始终使用友好的显示名称**。 确保您在数据视图中定义的所有字段（作为量度或维度组件）都具有友好的组件名称。 使用友好名称重命名字段的过程与来自Adobe Analytics源连接器数据集的字段特别相关。 这些字段通常具有不友好的不可识别名称，如`eVar41`或`prop25`。
* **使用特殊名称**。 当您在数据视图中将同一字段用作量度和维度组件时，独特名称特别相关。 或者，当您在同一类型的多个组件（例如，在两个不同的量度中）中使用字段时，每个组件都具有不同的组件设置。
* **使用组件命名约定**。 您可以使用组件命名惯例对组件进行分组。 例如，**[!UICONTROL 订单|产品]**&#x200B;和&#x200B;**[!UICONTROL 订单|客户]**&#x200B;可以区分数据中可能存在的不同订单量度。
* **使用数据字典**。 在数据字典中添加组件的描述和其他相关数据。 Data Insights Agent当前不使用数据字典中的描述和标记，但将来可能会使用。
* **使用批准的计算指标**。 同意一个流程，仅将批准的计算指标用作数据视图中的组件，并避免使用实验性的计算指标。
* **共享所需的区段**。 确保共享区段并显示Data Insights Agent提示所需的区段。
* **跨数据视图标准化组件名称**。 如果在多个数据视图中使用与组件相同的字段，请确保为该组件使用单个友好名称和单个标识符。 通过单个名称和标识符，Data Insights Agent可以切换数据视图而不会丢失上下文。


>[!MORELIKETHIS]
>
>[组件设置](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-dataviews/component-settings/overview)
>[数据字典](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/data-dictionary/data-dictionary-overview)
>[批准计算量度](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/cja-calcmetrics/cm-workflow/cm-approving)
>[共享区段](https://experienceleague.adobe.com/zh-hans/docs/analytics-platform/using/cja-components/segments/seg-share)
