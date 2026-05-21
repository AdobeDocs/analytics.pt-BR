---
title: Páginas não encontradas (métricas)
description: O número de ocorrências que contém um erro.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
TQID: https://experienceleague.adobe.com/V5jVT8wh71qMrchQmmM6c4EMofHPUEI388TmAf7Zf6M
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 139
ht-degree: 35%

---

# Páginas não encontradas

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma métrica. Consulte a página de dimensão [Páginas não encontradas](../dimensions/pages-not-found.md) para obter mais informações sobre como ela funciona como uma dimensão.*

A [métrica](overview.md) de &quot;Páginas não encontradas&quot; mostra o número de ocorrências em que uma dimensão foi definida ou mantida no momento em que um visitante encontrou um erro. Essa métrica é importante quando você quer ver quais páginas ou URLs contêm mensagens de erro (como 404). Em seguida, você pode transmitir essas informações para a equipe de desenvolvimento da Web, que pode determinar a causa do erro e corrigi-lo.

## Como essa métrica é calculada

Essa métrica conta todas as ocorrências em que a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md) é igual ao valor de `"errorPage"`. É o equivalente métrico da dimensão [Páginas não encontradas](../dimensions/pages-not-found.md).
