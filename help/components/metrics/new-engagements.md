---
title: Novos engajamentos
description: O número de vezes que um canal de primeiro contato é definido.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# Novos engajamentos

A [métrica](overview.md) de &quot;Novos engajamentos&quot; mostra o número de vezes que um visitante corresponde a um canal de marketing pela primeira vez durante o período de engajamento do visitante. Essa métrica é útil para comparar qualquer dimensão com um visitante que coincide com uma regra de processamento de canal de marketing pela primeira vez.

## Como essa métrica é calculada

Durante o processamento de dados, cada ocorrência passa pelas [Regras de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Se uma ocorrência corresponder a qualquer regra de processamento de canal de marketing e o visitante ainda não tiver um canal de primeiro contato, a ocorrência será um novo engajamento. Se uma ocorrência não corresponder a nenhuma regra de processamento de canal de marketing ou se o visitante já tiver um canal de primeiro contato, a ocorrência não será um novo engajamento.

Os visitantes podem ter mais que um novo engajamento se deixarem o período de engajamento do visitante expirar.
