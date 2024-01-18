---
title: Taxa de rejeição
description: A proporção de visitas com exatamente uma ocorrência pelo número de entradas.
feature: Metrics
exl-id: 2d4929df-3843-4ad2-abe6-5c01d3eac557
source-git-commit: ff3e9059d41f6365b850839a1f01c5747dcb9112
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 9%

---

# Taxa de rejeição

A &quot;Taxa de rejeição&quot; [métrica](overview.md) mostra a proporção de visitas que continham exatamente uma ocorrência em comparação ao número de visitas inseridas nessa página. Essa métrica pode ser utilizada para entender quais itens de dimensão têm a maior taxa de rejeição, ou para ver a taxa de rejeição total do site coletada ao longo do tempo. As altas taxas de rejeição podem esclarecer problemas com seu site ou aplicativo, como: design insatisfatório, tempos de carregamento lentos, conteúdo irrelevante ou uma incompatibilidade entre a intenção do visitante e o conteúdo da página.

Aqui está um exemplo: digamos que a página inicial de um site receba 500 visitantes em um mês. No entanto, 250 desses visitantes saem do site após visualizar a página inicial e não prosseguem para nenhuma outra página. Como resultado, a taxa de rejeição da página inicial seria de 50%.

>[!TIP]
>
>Use essa métrica junto com outra métrica, como [Entradas](entries.md), para obter melhores insights. Se essa métrica for utilizada sozinha, é possível obter itens de dimensão que contêm taxas de rejeição anômalas.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula [Rejeições](bounces.md) dividido por [Entradas](entries.md).
