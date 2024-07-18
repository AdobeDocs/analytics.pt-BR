---
title: Taxa de rejeição
description: A proporção de visitas com exatamente uma ocorrência pelo número de entradas.
feature: Metrics
exl-id: 2d4929df-3843-4ad2-abe6-5c01d3eac557
source-git-commit: ff3e9059d41f6365b850839a1f01c5747dcb9112
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 100%

---

# Taxa de rejeição

A [métrica](overview.md) “Taxa de rejeição” mostra a proporção de visitas que continham exatamente uma ocorrência em relação ao número de visitas nessa página. Você pode usar essa métrica para entender quais itens de dimensão têm a taxa de rejeição mais alta ou para ver uma taxa de rejeição total agregada do seu site ao longo do tempo. As altas taxas de rejeição podem esclarecer problemas com seu site ou aplicativo, como: design insatisfatório, tempos de carregamento lentos, conteúdo irrelevante ou uma incompatibilidade entre a intenção do visitante e o conteúdo da página.

Por exemplo: digamos que a página inicial de um site receba 500 visitantes em um mês. No entanto, 250 desses visitantes saem do site após visualizar a página inicial e não prosseguem para nenhuma outra página. Como resultado, a taxa de rejeição da página inicial seria de 50%.

>[!TIP]
>
>Use essa métrica junto com outra métrica, como [Entradas](entries.md), para obter insights melhores. Se você usar essa métrica sozinha, é possível obter itens de dimensão que contenham taxas de rejeição anômalas.

## Como essa métrica é calculada

Essa métrica é calculada usando a fórmula de [Rejeições](bounces.md) dividida pelas [Entradas](entries.md).
