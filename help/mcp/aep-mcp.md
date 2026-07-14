---
title: CX Co-worker Gateway中的Adobe Experience Platform工具
description: 通过CX Co-worker Gateway了解哪些Adobe Experience Platform工具可用。
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 8%

---


# Adobe CX Co-worker Gateway中的Adobe Experience Platform工具 {#aep-mcp}

您可以使用Adobe Experience Platform产品工具从与MCP兼容的客户端检查架构、数据集、数据管理配置、查询服务资源和审核事件。 当您的组织已启用，并且您的用户帐户具有所需的Experience Platform权限时，可以通过[Adobe CX Co-worker Gateway](overview.md)使用这些工具。

>[!AVAILABILITY]
>
>Experience Platform产品工具位于Beta中。 访问仅通过邀请进行，并且需要Adobe组织启用。 请参阅[访问CX Co-worker网关工具](access.md)。

## 概要

| 工具 | 描述 | 资源 | 功能 | 状态 |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | 检索查询服务IP访问限制 | 数据Distiller身份验证· IP范围 | list | 活动 |
| `search_audit` | 列出Experience Platform中的用户活动审核事件 | 审核查询·审核事件 | 列表，按资源类型筛选，操作，状态，时间范围 | 活动 |
| `search_datasets` | 查询数据集和批量摄取元数据 | 目录API ·数据集、批次 | 列表，获取，筛选，列出最后一个，列出文件 | 活动 |
| `search_class_relations` | 搜索Experience Platform企业级关系 | 类关系·静态YAML索引 | 按令牌、多词、部分匹配搜索 | 活动 |
| `search_data_access` | 列出失败摄取批次中的文件 | 数据访问API ·失败的批处理 | 列出失败的文件 | 活动 |
| `search_data_lake` | 检查数据集元数据和批次运行状况 | Data Lake API ·数据集、批次 | 获取，获取大小，列出失败的批次 | 活动 |
| `search_dule` | 查询数据管理标签、策略和操作 | 数据管理·标签、策略、营销活动 | 列表，获取，列表启用，评估 | 活动 |
| `search_query_service` | 查询SQL查询、模板、计划、警报 | 查询服务·查询、模板、计划、警报 | 列表，获取，筛选，获取连接参数 | 活动 |
| `search_schema_registry` | 查询XDM架构、字段组、类、类型 | 架构注册表·架构、字段组、类、数据类型、描述符 | 列表，获取，按容器筛选 | 活动 |

## 工具引用

### search_allowed_ip_ranges

**资源：**&#x200B;数据Distiller身份验证· IP范围
**状态：**&#x200B;活动

在当前沙盒中为查询服务检索所有配置的IP访问限制。 返回组织ID和允许的IP范围列表。 仅适用于具有Data Distiller加载项的客户。

**功能：**&#x200B;列出查询服务的允许IP范围

无参数。

### search_audit

**资源：**&#x200B;审核查询·审核事件
**状态：**&#x200B;活动

列出跨Experience Platform服务的用户活动带有时间戳的记录。 返回操作类型、用户电子邮件、资产信息和事件状态。 使用`asset_type`和`action`缩小结果范围。 未指定时间范围时，默认为最近7天。 限于过去90天的最近1000条记录和事件。

**功能：**&#x200B;列出审核事件，按资源类型筛选，操作，状态，时间范围，分页

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `action` | 否 | 按操作类型过滤。 常用值（OR以逗号分隔）： `Create`， `Delete`， `Update`， `Enable`， `Disable` |
| `asset_type` | 否 | 按资源类型筛选。 必须为： `Dataset`、`Schema`、`Segment`、`Destination`、`Source Data Flow`、`Merge Policy`、`Identity Namespace`、`Identity Graph`、`Sandbox`、`Role`、`Query`、`Scheduled Query`、`Datastream`、`Computed Attribute`、`Field Group`、`Class`、`Data Types`、`Account`、`Product Profile`、`Query Template`、`Work Order`、`Audit Logs`、`Access Control Policy`之一 |
| `status` | 否 | 按事件状态筛选。 值： `Success`、`Failure`、`Allow`、`Deny`。 OR的逗号分隔 |
| `start_time` | 否 | 最早的时间戳。 ISO 8601 UTC和ms，例如`2024-01-15T00:00:00.000Z` |
| `end_time` | 否 | 最新时间戳。 ISO 8601 UTC，带ms |
| `property_filter` | 否 | 原始筛选器表达式，如`action==create`。 首选上述专用参数 |
| `orderby` | 否 | 排序顺序： `timestamp` (asc)或`-timestamp` (desc) |
| `limit` | 否 | 最大结果数（3-1000，默认为50） |
| `start` | 否 | 分页偏移。 每页按限制值递增 |
| `query_id` | 否 | 来自先前响应的查询ID以重复相同查询 |

### search_dataset

**资源：**&#x200B;目录API ·数据集、批次
**状态：**&#x200B;活动

Experience Platform目录服务的统一调度工具。 查询数据集元数据（架构引用、标记、创建信息）或批量摄取记录（状态、量度、文件列表）。 使用`dataset/list`发现数据集，`batch/list`检查摄取运行状况，以及`batch/list_files`或`batch/get_meta_files`检查特定批次内容。 所有操作均为只读。

**功能：**&#x200B;列出数据集，获取数据集，列出批次，获取批次，为每个数据集列出上一批次，列出批处理文件，获取批处理元文件（行错误，输入文件）

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `entity_type` | 是 | `dataset` 或 `batch` |
| `operation` | 是 | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. 有效的组合：数据集→ list， get；批次→全部五个 |
| `resource_id` | 否 | 数据集或批次ID。 `dataset/get`、`batch/get`、`batch/list_files`、`batch/get_meta_files`必需 |
| `query_params.limit` | 否 | 每页最大结果数（最多100个）。 应用于所有列表操作 |
| `query_params.start` | 否 | 分页偏移。 应用于所有列表操作 |
| `query_params.order_by` | 否 | 排序方向，如`asc:created,updated`。 应用于所有列表操作 |
| `query_params.properties` | 否 | 逗号分隔的属性允许列表。 适用于数据集/列表、数据集/获取、批处理/列表、批处理/list_last |
| `query_params.name` | 否 | 按名称筛选数据集（仅限数据集/列表） |
| `query_params.tags` | 否 | 按标记（如`unifiedProfile:enabled:true`）筛选数据集 （仅限数据集/列表） |
| `query_params.property_filter` | 否 | 对响应对象（数据集/列表和批处理/列表）进行正则表达式筛选 |
| `query_params.status` | 否 | 按状态筛选批次： `success`、`failed`、`loading`、`active`（仅限批次/列表） |
| `query_params.dataset_id` | 否 | 将批次范围设定为特定数据集（批次/列表和batch/list_last） |
| `query_params.created_after` | 否 | 筛选在Unix时间戳之后创建的批次（以毫秒为单位）（仅限批次/列表） |
| `query_params.created_before` | 否 | 筛选在Unix时间戳之前（以毫秒为单位）创建的批次（仅限批次/列表） |
| `query_params.last_batch_status` | 否 | 按上一批次状态筛选（仅限batch/list_last） |
| `query_params.aggregate` | 否 | 返回根级别的汇总量度（仅限批处理/获取） |
| `query_params.path` | 否 | 要下载的Meta文件： `row_errors`、`input_files`、`row_errors_sample.json`（仅限batch/get_meta_files） |

### search_class_relations

**资源：**&#x200B;类关系·静态YAML索引
**状态：**&#x200B;活动

使用静态`class_relations_v1.yaml`索引按名称搜索Experience Platform业务类关系。 未调用Experience Platform API。 接受单个术语或以逗号分隔的术语；每个术语使用部分令牌匹配根据类名进行匹配。 返回具有正向关系（每个类指向的内容）和反向关系（哪些类指向它）的匹配类。 在构建查询、数据流或架构组合之前，请使用此项了解实体关系。

**功能：**&#x200B;按令牌搜索、多词逗号分隔搜索、部分令牌匹配、双向同义词扩展

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `query` | 是 | 要搜索的业务类名称或对象类型。 支持部分令牌匹配（`dat`与`dataset`、`data_type`等匹配）。 传递多个以逗号分隔的词以同时搜索多个类（例如`dataset, schema`） |
| `n` | 否 | 要返回的最大匹配结果数（默认为5，最小为1） |

### search_data_access

**资源：**&#x200B;数据访问API ·失败的批处理
**状态：**&#x200B;活动

从失败的Experience Platform数据摄取批次访问文件。 使用`failed_batch/list_failed`列出属于失败批次的文件以进行故障诊断。 所有操作都需要批次ID。 注意： `file/get`和`dataset/preview`已禁用，因为它们公开实际记录数据。 所有操作均为只读。

**功能：**&#x200B;从失败的引入批次中列出文件

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `entity_type` | 是 | `failed_batch` — 列出失败引入批次中的文件 |
| `operation` | 是 | `list_failed` — 唯一支持的操作 |
| `resource_id` | 是 | 失败批次的批次ID |
| `query_params.start` | 否 | 分页起始索引，如`1` |
| `query_params.limit` | 否 | 每页的结果数，如`10` |
| `query_params.path` | 否 | 完整文件名筛选器，如`profiles.csv` |


### search_data_lake

**资源：**&#x200B;数据湖API ·数据集，批次
**状态：**&#x200B;活动

检查数据湖层中的数据集并批处理元数据。 使用`get`表示完整的元数据，使用`get_size`表示存储和摄取大小量度，使用`list_failed`监视时间范围内的摄取失败。 如果未为`list_failed`提供时间范围，则默认为过去7天。 所有操作均为只读，需要资源ID。

**功能：**&#x200B;获取数据集/批次元数据，获取存储大小量度，在一个时间范围内列出失败的批次

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `entity_type` | 是 | `dataset` 或 `batch` |
| `operation` | 是 | `get`, `get_size`, `list_failed`. `list_failed`仅支持`batch`实体类型 |
| `resource_id` | 是 | 数据集ID或批次ID。 对于`list_failed`：要将故障范围设定为的数据集ID |
| `query_params.created_after` | 否 | 时间窗口的开始。 Unix时间戳（以毫秒为单位） |
| `query_params.created_before` | 否 | 时间窗口结束。 Unix时间戳（以毫秒为单位） |
| `query_params.limit` | 否 | 每页最大结果数（最多100个） |
| `query_params.order_by` | 否 | 排序方向，如`desc:created` |

### search_dule

**资源：**&#x200B;数据管理·标签、策略、marketing_actions
**状态：**&#x200B;活动

查询策略服务API，以获取数据使用标签、策略和营销操作。 使用`marketing_action/evaluate`测试对具有特定标签的数据的营销操作是否会违反任何治理策略。 所有操作均为只读。

**功能：**&#x200B;列出/获取数据使用标签，列出/获取策略，列出启用的策略，列出/获取营销操作，根据标签评估营销操作

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `entity_type` | 是 | `label`、`policy`或`marketing_action` |
| `operation` | 是 | `list`、`get`、`list_enabled`（仅限策略）、`evaluate`（仅限于marketing_action）。 `list_enabled`不需要作用域 |
| `scope` | 否 | `core` （Adobe定义）或`custom` （组织定义）。 `list`、`get`、`evaluate`必需；未用于`list_enabled` |
| `resource_id` | 否 | 标签名称、策略ID或营销操作名称。 `get`和`evaluate`必需 |
| `query_params.dule_labels` | 否 | 逗号分隔的标签（如`C1,C3`）。 `marketing_action/evaluate`必需；`policy/list`的可选筛选器 |
| `query_params.limit` | 否 | 最大结果 |
| `query_params.start` | 否 | 来自先前响应的`_page.next`值的分页光标 |
| `query_params.orderby` | 否 | 逗号分隔的排序字段 |
| `query_params.property_filter` | 否 | 筛选表达式，如`name==C1` |
| `query_params.marketing_action` | 否 | 将策略列表限制为引用此营销操作的策略（仅限策略/列表） |
| `query_params.include_draft` | 否 | 在`marketing_action/evaluate`中包含草稿策略（默认：仅启用策略） |

### search_query_service

**资源：**&#x200B;查询服务·查询、模板、计划、计划运行、连接、警报订阅
**状态：**&#x200B;活动

查询服务资源的统一工具。 列出和检索临时查询、保存的SQL模板、计划的查询及其运行、交互式连接参数（用于psql/JDBC客户端）和警报订阅。 对于查询列表，默认为`isService==false,isParentLevel==true`以过滤掉内部流量。 所有操作均为只读。

**功能：**&#x200B;列表/获取查询、列表/获取模板、列表/获取计划、列表/获取计划运行、获取连接参数、列出警报订阅

**参数：**

| 参数 | 必需 | 描述 |
| --- | --- | --- |
| `entity_type` | 是 | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | 是 | `list`, `get`, `get_connection_params`, `list_by_u...` |
