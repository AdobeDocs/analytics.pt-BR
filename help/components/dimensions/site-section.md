---
title: Seção do site
description: O nome da seção do site.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 90%

---

# Seção do site

A [dimensão](overview.md) de &#39;Seção do site&#39; lista os nomes das seções do site. Para sites grandes, é útil agrupar páginas em seções. Essa dimensão é útil para ver as seções de site com melhor desempenho ou as mais exibidas.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Servidor](server.md). A dimensão Página é mais granular, a dimensão Servidor é menos granular e a dimensão Seção do site fica entre as duas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`ch` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável [`channel`](/help/implement/vars/page-vars/channel.md).

## Itens de dimensão

Os itens de dimensão incluem os nomes das seções do site. A organização escolhe quais itens de dimensão específicos quer utilizar. Independentemente do método usado, verifique se ele é consistente e registre-o em um [documento de design de solução](/help/implement/prepare/solution-design.md).
