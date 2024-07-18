---
title: Instâncias
description: O número de ocorrências a que uma variável foi definida (e não persistiu).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 813d209980ad02c412970a698c282c1358921ed6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 50%

---

# Instâncias

A [métrica](overview.md) de &quot;Instâncias&quot; mostra o número de vezes que uma dimensão foi explicitamente definida em uma solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem itens de dimensão após a ocorrência em que estão definidas. Essa métrica é útil quando você deseja ver o número de vezes que um item de dimensão foi definido sem as ocorrências nas quais esse valor persistiu.

## Como essa métrica é calculada

De todas as ocorrências em um conjunto de relatórios, inclua somente ocorrências que definam explicitamente um item de dimensão na solicitação de imagem. Algumas dimensões, como [eVars](../dimensions/evar.md), persistem além da ocorrência em que estão definidas. Métricas como [Visualizações de página](page-views.md) e [Ocorrências](occurrences.md) contam valores iniciais e persistentes. Essa métrica não conta valores persistentes.

Por exemplo, um visitante chega ao seu site e usa pesquisa interna. Você rastreia a pesquisa interna em eVar 1. Depois de usar a pesquisa interna uma vez, eles visitam mais cinco páginas antes de sair.

Ao exibir um relatório no Workspace, você veria uma instância do eVar1 e seis ocorrências. Uma instância conta na página de resultados da pesquisa, enquanto a métrica de ocorrências conta o valor inicial e os valores persistentes subsequentes.

## Comparar a métricas semelhantes

* **Instâncias vs. [Ocorrências](occurrences.md)**: as instâncias não incluem ocorrências nas quais um item de dimensão é mantido. A métrica Ocorrências conta ocorrências em que um item de dimensão foi definido ou mantido.
* **Instâncias versus [Exibições de página](page-views.md)**: as instâncias incluem todos os tipos de ocorrência, incluindo chamadas de rastreamento de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)), chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) e dados de resumo [Fontes de dados](/help/import/data-sources/overview.md). A métrica Exibições de página inclui apenas chamadas de rastreamento de exibição de página, e não inclui chamadas de rastreamento de link ou fontes de dados de resumo.
