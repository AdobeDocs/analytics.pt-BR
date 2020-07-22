---
title: Tempo médio no site
description: A quantidade média de tempo que um determinado item de dimensão existiu entre as ocorrências.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 1%

---


# Tempo médio no site

A métrica &#39;Tempo médio no site&#39; mostra o tempo decorrido entre as ocorrências de um determinado item de dimensão. Essa métrica é útil quando você deseja ver o tempo médio gasto para itens de dimensão específicos. Você também pode analisar a tendência dessa métrica ao longo do tempo para ver como o tempo total gasto muda. Essa métrica é exibida no `HH:MM:SS` formato.

Essa métrica está relacionada à dimensão [Tempo gasto por visita](../dimensions/time-spent-per-visit.md) .

## Como essa métrica é calculada

Para um determinado item de dimensão, use o carimbo de data e hora de cada ocorrência em que o item de dimensão existe. Compare-o com o carimbo de data e hora da próxima ocorrência na visita. Se a ocorrência não tiver uma ocorrência subsequente, não a inclua nessa métrica. De todo o tempo gasto para o item de dimensão, divida-os todos pelo número de &quot;sequências&quot; para esse item de dimensão. Uma &quot;sequência&quot; é onde um item de dimensão é o mesmo para uma ou mais ocorrências consecutivas. Esse número resultante é a métrica exibida nos relatórios.

Por exemplo, considere a seguinte visita:

| `Timestamp` | `Page` |
| --- | --- |
| `12:03:00` | `Home page` |
| `12:04:20` | `Product page A` |
| `12:05:30` | `Product page A` |
| `12:07:00` | `Product page B` |
| `12:07:40` | `Product page A` |
| `12:08:10` | `Checkout` |
| `12:10:00` | `Purchase` |
| `12:25:00` | `Home page` |
| `12:25:40` | `Product page A` |


Se desejar tempo médio no site para o item de dimensão `Product page A`, considere primeiro a quantidade de tempo decorrido entre as ocorrências para essa dimensão:

* **12:04:20 - 12:05:30** - 1 minuto 10 segundos
* **12:05:30 - 12:07:00** - 1 minuto 30 segundos
* **12:07:40 - 12:08:10** - 30 segundos
* **12:25:40 - ?** - Não incluído

O tempo total gasto `Product page A` é `00:03:10`. Houve duas sequências nessa visita. a primeira sequência para os dois valores consecutivos e a segunda antes do check-out. A última ocorrência da visita não é uma sequência, pois não há carimbo de data e hora final.

O tempo médio no site para `Product page A` é `00:01:35`.

## Tempo médio gasto no site (segundos)

A métrica &#39;Tempo médio gasto no site (segundos)&#39; mostra os mesmos dados apresentados como um número inteiro em vez de no `HH:MM:SS` formato. Essa métrica é mais valiosa como um componente dentro das métricas calculadas.

## Os totais de detalhamento não correspondem ao item de linha pai

A métrica &#39;Tempo médio no site&#39; usa sequências não quebradas de uma determinada dimensão. A dimensão de detalhamento não depende da dimensão pai ao calcular essas sequências. Por exemplo, considere a seguinte visita:

| `Timestamp` | `Page name` | `Site section` |
| --- | --- | --- |
| `12:00:00` | `Home` | `Foxes` |
| `12:00:30` | `Product` | `Foxes` |
| `12:02:10` | `Home` | `Foxes` |
| `12:02:20` | `(None; exit link click)` | `(None; exit link click)` |

O cálculo do tempo médio no site para o item de dimensão `Home` usaria o seguinte cálculo:

```text
(30 + 10) / 2 = 20 seconds average time on site
```

Se você aplicasse um detalhamento usando a dimensão de seções [do](../dimensions/site-section.md) Site, ele usaria o seguinte cálculo:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Como havia uma única sequência na dimensão de detalhamento, ela usa um denominador diferente de sua dimensão pai. Normalmente, essas métricas fornecem resultados semelhantes em nível de visita, mas podem ser diferentes em nível de ocorrência.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo médio de toda a dimensão no site, e o numerador é o tempo médio do item de dimensão no site. Se o tempo médio de toda a dimensão no site for menor que o tempo médio de um determinado item de dimensão no site, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra o tempo médio da anomalia nos valores do site, que normalmente não é valioso. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte Visão geral [do](time-spent.md) Tempo gasto para obter mais informações gerais sobre o tempo gasto.
