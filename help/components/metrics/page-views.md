---
title: Exibições de página
description: O número de vezes que um item de dimensão foi definido ou mantido no Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 18%

---

# Exibições de página

A variável **[!UICONTROL Exibições de página]** métrica mostra o número de vezes que um determinado item de dimensão (valor de dimensão) foi definido ou persistiu (ou seja, quando expira) em uma página. É uma das métricas mais comuns e básicas nos relatórios.

Por exemplo, a variável [!UICONTROL Dias da semana] A dimensão é composta pelos seguintes itens de dimensão: domingo, segunda-feira, terça-feira, quarta-feira, quinta-feira, sexta-feira e sábado.

## Como essa métrica é calculada

Essa métrica conta todas as chamadas de rastreamento de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) em um conjunto de relatórios. Para dimensões, inclui ocorrências em que um item de dimensão é definido ou persistente. Ela não inclui chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) ou dados do resumo [Fontes de dados](/help/import/data-sources/overview.md).

## Comparar a métricas semelhantes

* **Exibições de página versus [Visitas](visits.md)**: As exibições de página contam o número de vezes que uma página é exibida. A contagem de visitas é o número de sessões para visitantes. Uma visita pode consistir em uma ou mais exibições de página.
* **Exibições de página versus [Eventos de página](page-events.md)**: as exibições de página contam o número de chamadas de rastreamento de exibição de página (`t()`) e exclui chamadas de rastreamento de link (`tl()`). Eventos de página são o oposto; eles contam o número de chamadas de rastreamento de link e excluem chamadas de rastreamento de visualização de página.
