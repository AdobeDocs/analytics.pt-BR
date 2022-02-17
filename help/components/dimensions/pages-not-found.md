---
title: Páginas não encontradas
description: URLs que retornaram um erro ao site.
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 100%

---

# Páginas não encontradas

*Esta página de ajuda descreve como a métrica &quot;Páginas não encontradas&quot; funciona como uma dimensão. Consulte a métrica [Páginas não encontradas](../metrics/pages-not-found.md) para obter mais informações.*

A dimensão “Páginas não encontradas” exibe URLs que continham um erro. Essa dimensão é útil para diminuir o número de erros que o visitante recebe no site.

* É possível utilizar essa dimensão em uma [Visualização de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) para ver em quais páginas os visitantes clicam para chegar ao erro. Em seguida, você pode trabalhar com equipes de desenvolvimento em sua organização para corrigir o link em cada página.
* É possível utilizar essa dimensão com a dimensão [“Referenciador”](referrer.md) para ver o lugar no site que os visitantes chegam quando eles vêm de links externos. É possível implementar redirecionamentos para o local desejado ou trabalhar com terceiros para corrigir o link.

## Preencher esta dimensão com dados

Essa dimensão recupera dados de [`pageType` e das `g` sequências de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. Se a sequência de consulta `pageType` for igual a `errorPage`, a sequência de consulta `g` (URL da página) será registrada. O AppMeasurement coleta esses dados usando a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md). Se a variável `pageType` não estiver definida ou programada como algo diferente de `errorPage`, nenhum dado para essa dimensão será coletado.

## Itens de dimensão

Os itens de dimensão incluem os URLs das páginas do site em que ocorreu um erro.
