---
title: Data Engineering Agent
description: 了解如何使用Data Engineering Agent。
hide: true
hidefromtoc: true
source-git-commit: 12c61f88b358fc8c357ec4fa373493d6b70d5a06
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 1%

---

# Data Engineering Agent

&lt;! — 这是草稿 — >

Data Engineering Agent是Agent Orchestrator支持的、基于AI的协同试点，适用于Adobe Experience Platform中的数据团队。 该代理旨在处理整个端到端数据生命周期中的繁重工作：数据建模、上线、SQL数据准备、治理和生命周期管理。 借助Data Engineering Agent，工程师和架构师能够以更高的数据质量和更少的手动工作更快地移动。

Data Engineering Agent包含多种技能，您可以利用这些技能优化工作流。

| Data Engineering Agent技能 | 描述 |
| --- | --- |
| 数据载入 | <strong>数据载入</strong>支持S3、Marketo和数据登陆区(DLZ)等批处理源。 其功能包括： <ul><li>连接到各种数据源，包括S3、Data Landing Zone、Marketo等。</li><li>分析源数据（例如，不同的值、空值、重复项和基本质量量度）。</li><li>将源字段与标准XDM字段组和自定义字段对齐。</li><li>提议和构建数据摄取数据流(例如，将数据从S3或Marketo移动到RTCDP/CJA数据集中)。</li></ul> |
| 自动化数据质量和语义扩充 | <ul><li>执行全面的数据质量评估，包括识别异常和报告有效/无效的记录计数。</li><li>建议进行数据质量改进，例如类型标准化、货币格式设置和ID重复数据删除。</li><li>将语义扩充应用于基于数据采样和智能命名模式识别的架构。</li><li>让用户确认建议的增强功能，确保最终确定和批准的数据更改。</li></ul> |
| 数据蒸馏器 | |
| 数据收集 | |
| 数据验证 | |

借助Data Engineering Agent，您可以确保：

- **更快上线**：将时间从几周的手动架构映射和管道设置减少到几小时的引导式对话式配置。
- **数据质量更高**：由于内置的数据质量分析和语义检查，无效记录和生产事件减少。
- **改进的治理和合规性**：治理策略在设计时附加（标签、TTL、身份处理），而不是作为事后考虑附加的。
- **更高效的数据团队**：重复的SQL/数据流工作已自动化，因此工程师将重点放在更高价值的设计和优化上。
- **更广泛的自助服务**：非专家利益相关者可以安全地使用护栏自助执行常见的数据准备任务。