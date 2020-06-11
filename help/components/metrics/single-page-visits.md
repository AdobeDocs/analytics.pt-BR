---
title: Visitas únicas à página
description: O número de vezes que o valor da dimensão 'Página' não foi alterado em uma visita.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---


# Visitas únicas à página

*Esta página de ajuda descreve como &quot;Visitas únicas à página&quot; funciona como uma métrica. Consulte a dimensão Visitas[](../dimensions/single-page-visits.md)únicas à página para obter mais informações.*

A métrica &quot;Visitas únicas à página&quot; mostra o número de visitas nas quais o valor da dimensão [Página](../dimensions/page.md) continha apenas um único valor exclusivo para toda a visita. Essa métrica é útil no contexto de dimensões nas quais você deseja visualizar visitas curtas, mas não tem regras tão rigorosas quanto [Rejeições](bounces.md).

## Como essa métrica é calculada

Essa métrica conta o número de visitas nas quais o valor da dimensão &quot;Página&quot; continha apenas um único valor exclusivo para toda a visita. Se um visitante recarregar a página ou acionar chamadas de rastreamento de link, ainda será contado como uma visita de página única. Assim que a dimensão Página mudar para um segundo valor exclusivo, a visita não se qualificará mais como uma visita de página única.

Consulte [Acesso](single-access.md) único para obter uma comparação entre as métricas.
