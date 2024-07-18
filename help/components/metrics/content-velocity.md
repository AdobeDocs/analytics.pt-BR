---
title: Velocidade do conteúdo
description: A velocidade do conteúdo mede seu impacto no conteúdo downstream.
feature: Metrics
exl-id: 8ba54990-ff7d-4693-92de-7f9d9f916b55
source-git-commit: 26e166e065df90cb327fe1106542e17831069141
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 19%

---

# Velocidade do conteúdo

A métrica calculada &quot;Velocidade do conteúdo&quot; ajuda a medir como uma dimensão (normalmente [[!UICONTROL Página]](/help/components/dimensions/page.md)) contribui para que os usuários gastem tempo no seu site ou aplicativo.

Esta métrica usa a [Atribuição de participação](/help/analyze/analysis-workspace/attribution/models.md) na métrica [Exibições de página](page-views.md) como parte de seu cálculo. Com a participação da Visita, toda vez que uma página é acessada, todas as páginas que foram acessadas anteriormente durante a mesma visita também recebem crédito pela exibição da página. Normalmente, essa fórmula significa que, quanto mais cedo uma página for acessada durante uma visita, mais crédito ela receberá. (Consulte [Exibições de página (Participação) | Visita) ou &#39;Participação na visita&#39;](#page-views-participation--visit-or-visit-participation) para obter mais informações.)

## Cálculo

&#39;Velocidade do conteúdo&#39; é uma [métrica](overview.md) calculada padrão e usa a fórmula `Page views (Visit participation)` dividida por `Visits`.

![](assets/cont-velo-1.png)

## Usos comuns

[!UICONTROL A velocidade do conteúdo] é normalmente utilizada na análise do conteúdo juntamente com outras métricas principais, como [!UICONTROL Visualizações de página], [!UICONTROL Visitas] e [!UICONTROL Taxa de rejeição].

![](assets/cont-velo-3.png)

## Exemplo

O exemplo a seguir detalha as 2 partes da Velocidade do conteúdo: &quot;Visualizações de página (Participação | Visita)&quot; e &quot;Visitas&quot;.

### Exibições de página (participação) | Visita) ou &quot;Participação na visita&quot;

Considere o exemplo a seguir de como a participação da visita afeta a atribuição:

Em um site, um usuário visita as seguintes páginas nesta ordem:

* Página A
* Página B
* Página C
* Página D

No exemplo acima, a Página A receberia crédito por 4 ocorrências, a Página B por 3 ocorrências, a Página C por 2 ocorrências e a Página D por 1 ocorrência.

O exemplo a seguir ilustra o mesmo princípio, mas com algumas páginas sendo visitadas mais de uma vez.

* Página A
* Página B
* Página C
* Página B
* Página D
* Página A

No exemplo acima, a Página A receberia crédito por 7 ocorrências, a Página B por 8 ocorrências, a Página C por 4 ocorrências e a Página D por 2 ocorrências.

### Visitas

Depois que a participação da visita é calculada, o resultado é dividido pelo número de visitas.
