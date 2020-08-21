---
title: Visitas em única página
description: O número de vezes que o item de dimensão 'Página' não foi alterado em uma visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 62%

---


# Visitas em única página

*Esta página de ajuda descreve como a dimensão “Visitas em única página” funciona como uma métrica. Consulte a dimensão[Visitas em única página](../dimensions/single-page-visits.md)para obter mais informações.*

The &#39;Single page visits&#39; metric shows the number of visits where the [Page](../dimensions/page.md) dimension item contained only a single unique value for the entire visit. Essa métrica é útil no contexto de dimensões em que você deseja visualizar visitas curtas, mas não tem regras tão rigorosas quanto [Rejeições](bounces.md).

## Como essa métrica é calculada

Essa métrica conta o número de visitas nas quais o item de dimensão &quot;Página&quot; continha apenas um único valor exclusivo para toda a visita. Se um visitante recarregar a página ou acionar chamadas de rastreamento de link, ainda será contado como uma visita de página única. Assim que a dimensão Página mudar para um segundo valor exclusivo, a visita não se qualificará mais como uma visita de página única.

Consulte [Acesso único](single-access.md) para obter uma comparação entre as métricas.
