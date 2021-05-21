---
title: Tempo médio no site
description: A quantidade média de tempo em que um determinado item de dimensão existia entre ocorrências.
exl-id: bf9056e2-4f6d-4c4f-b641-d3146ce269ff
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '538'
ht-degree: 100%

---

# Tempo médio no site

A métrica “Tempo médio no site” mostra o tempo decorrido entre as ocorrências de um determinado item de dimensão. Essa métrica é útil quando você quiser ver o tempo médio gasto para itens de dimensão específicos. Você também pode analisar a tendência dessa métrica ao longo do tempo para ver como o tempo total gasto muda. Essa métrica é exibida no formato `HH:MM:SS`.

Essa métrica está relacionada à dimensão [Tempo gasto por visita](../dimensions/time-spent-per-visit.md).

## Como essa métrica é calculada

Para um determinado item de dimensão, use o carimbo de data e hora de cada ocorrência em que esse item de dimensão existe. Compare essa ocorrência com o carimbo de data e hora da próxima ocorrência da visita. Se a ocorrência não tiver uma ocorrência subsequente, não a inclua nessa métrica. De todo o tempo gasto para o item de dimensão, divida-os todos pelo número de “sequências” para esse item de dimensão. Uma “sequência” é onde um item de dimensão é o mesmo para uma ou mais ocorrências consecutivas. Esse número resultante é a métrica exibida nos relatórios.

Por exemplo, considere esta visita:

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


Se você quiser ver o tempo médio no site para o item de dimensão `Product page A`, primeiro pegue a quantidade de tempo decorrido entre as ocorrências dessa dimensão:

* **12:04:20 - 12:05:30** - 1 minuto 10 segundos
* **12:05:30 - 12:07:00** - 1 minuto 30 segundos
* **12:07:40 - 12:08:10** - 30 segundos
* **12:25:40 - ?** - Não incluído

O tempo total gasto para `Product page A` é `00:03:10`. Houve duas sequências nessa visita; a primeira sequência para os dois valores consecutivos e a segunda antes do check-out. A última ocorrência da visita não é uma sequência, pois não há carimbo de data e hora final.

O tempo médio no site para `Product page A` é `00:01:35`.

>[!NOTE]
>
>Essa métrica mostrará um valor de `"Invalid"` se o item de dimensão contiver somente ocorrências que foram as últimas em uma visita. Essa métrica exige uma ocorrência subsequente para rastrear o tempo gasto.

## Tempo médio gasto no site (segundos)

A métrica “Tempo médio gasto no site (segundos)” mostra os mesmos dados apresentados como um número inteiro em vez de no formato `HH:MM:SS`. Essa métrica é mais valiosa como um componente dentro das métricas calculadas.

## Os totais de detalhamento não correspondem ao item de linha principal

A métrica “Tempo médio no site” usa sequências contínuas de uma determinada dimensão. A dimensão de detalhamento não depende da dimensão principal ao calcular essas sequências. Por exemplo, considere esta visita:

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

Se você aplicasse um detalhamento usando a dimensão [Seções do site](../dimensions/site-section.md), ele usaria o seguinte cálculo:

```text
(30 + 10) / 1 = 40 seconds average time on site
```

Como havia uma única sequência na dimensão de detalhamento, ela usa um denominador diferente de sua dimensão principal. Normalmente, essas métricas fornecem resultados semelhantes no nível de visita, mas podem ser diferentes no nível de ocorrência.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é o tempo médio da dimensão inteira no site, e o numerador é o tempo médio do item de dimensão no site. Se o tempo médio de toda a dimensão no site for menor que o tempo médio de um dado item de dimensão no site, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra o tempo médio da anomalia nos valores do site, que normalmente não é importante. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.

Consulte [Visão geral do tempo gasto](time-spent.md) para obter mais informações gerais sobre o tempo gasto.
