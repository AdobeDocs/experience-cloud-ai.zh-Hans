---
title: AI助手中的隐私、安全和管理
description: 了解AI Assistant的隐私、安全和治理实践。
TQID: https://experienceleague.adobe.com/ViaEXSy4OEyTzSKlYAq0T6PbewPx1PJtyzE8E0wXbvM
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 239
ht-degree: 0%

---

# AI助手中的隐私、安全和管理

Adobe Experience Platform中的AI助手以隐私、安全和治理为原则。

请阅读本文档，了解您可以期待从AI Assistant获得的以客户信任为中心的功能：

* 目前，AI助手没有使用任何个人数据，即使用于培训目的也是如此。
* AI助手不知道消费者数据。
* AI助手将遵循所有现有的[访问控制](https://experienceleague.adobe.com/zh-hans/docs/experience-platform/access-control/home)策略。
   * 任何基于属性的新访问控制策略在最多24小时&amp;ast后反映在AI Assistant中；
* 在与Adobe Experience Platform Healthcare Shield结合使用时，AI Assistant是HIPAA就绪功能。
* 您可以查看之前与AI助手进行的交互的日志，保留策略为30天。
* AI助手在响应用户提示时基于特定于沙盒的数据和公共Adobe文档。 数据不会在沙盒之间共享。
* 您提供给AI助理的提示不会共享给其他客户。

&amp;ast； *这意味着如果向字段和对象添加任何新标签或创建任何新策略，则需要AI助手最多24小时才能兑现它们。 在这24小时内，新受限制访问的用户仍然可以访问这些字段和对象。*
