---
title: Páginas não encontradas
description: URLs que retornaram um erro em seu site.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Páginas não encontradas

*Esta página de ajuda descreve como &quot;Páginas não encontradas&quot; funciona como uma dimensão. Consulte a métrica[Páginas não encontradas](../metrics/pages-not-found.md)para obter mais informações.*

A dimensão &#39;Páginas não encontradas&#39; mostra URLs que continham um erro. Essa dimensão é útil quando você deseja diminuir o número de erros que o visitante recebe no site.

* Você pode usar essa dimensão em uma visualização [de](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) Fluxo para ver quais visitantes de páginas clicam para chegar ao erro. Em seguida, você pode trabalhar com equipes de desenvolvimento em sua organização para corrigir o link em cada página.
* Você pode usar essa dimensão com a dimensão [&#39;Quem indicou&#39;](referrer.md) para ver onde os visitantes chegam ao seu site a partir de links externos. Você pode implementar redirecionamentos para o local desejado ou trabalhar com terceiros para corrigir o link.

## Preencher esta dimensão com dados

Essa dimensão recupera dados das sequências de caracteres [`pageType` e `g` query](/help/implement/validate/query-parameters.md) em solicitações de imagem. Se a string do `pageType` query for igual `errorPage`, a string do `g` query (URL da página) será registrada. O AppMeasurement coleta esses dados usando a [`pageType`](/help/implement/vars/page-vars/pagetype.md) variável. Se a `pageType` variável não estiver definida ou definida como algo diferente de `errorPage`, nenhum dado para essa dimensão será coletado.

## Valores de dimensão

Os valores de dimensão incluem os URLs das páginas do site em que ocorreu um erro.
