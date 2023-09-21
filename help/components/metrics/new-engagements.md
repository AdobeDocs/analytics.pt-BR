---
title: Novos engajamentos
description: O número de vezes que um canal de primeiro contato é definido.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# Novos engajamentos

Os &quot;Novos engajamentos&quot; [métrica](overview.md) mostra o número de vezes que um visitante corresponde a um canal de marketing pela primeira vez durante o período de engajamento do visitante. Essa métrica é útil para comparar qualquer dimensão com um visitante que coincide com uma regra de processamento de canal de marketing pela primeira vez.

## Como essa métrica é calculada

Durante o processamento de dados, cada ocorrência passa pelas [Regras de processamento de canal de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Se uma ocorrência corresponder a qualquer regra de processamento de canal de marketing e o visitante ainda não tiver um canal de primeiro contato, a ocorrência será um novo engajamento. Se uma ocorrência não corresponder a nenhuma regra de processamento de canal de marketing ou se o visitante já tiver um canal de primeiro contato, a ocorrência não será um novo engajamento.

Os visitantes podem ter mais que um novo engajamento se deixarem o período de engajamento do visitante expirar.
