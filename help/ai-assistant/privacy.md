---
title: AI助手中的隐私、安全和管理
description: 了解AI Assistant的隐私、安全和治理实践。
source-git-commit: 96db2a481d08011139bba6e93b13c8f35420fb61
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 0%

---

# AI助手中的隐私、安全和管理

Adobe Experience Platform中的AI助手以隐私、安全和治理为原则。

请阅读本文档，了解您可以期待从AI Assistant获得的以客户信任为中心的功能：

* 目前，AI助手没有使用任何个人数据，即使用于培训目的也是如此。
* AI助手不知道消费者数据。
* AI助手将遵循所有现有的[访问控制](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/home)策略。
   * 任何基于属性的新访问控制策略在最多24小时&amp;amp；ast；之后反映在AI Assistant中；
* 在与Adobe Experience Platform Healthcare Shield结合使用时，AI Assistant是HIPAA就绪功能。
* 您可以查看之前与AI助手进行的交互的日志，保留策略为30天。
* AI助手在响应用户提示时基于特定于沙盒的数据和公共Adobe文档。 数据不会在沙盒之间共享。
* 您提供给AI助理的提示不会共享给其他客户。

&amp;amp；ast； *这意味着如果向字段和对象添加任何新标签或创建任何新策略，则需要AI助手最多24小时才能兑现它们。 在这24小时内，新受限制访问的用户仍然可以访问这些字段和对象。*
