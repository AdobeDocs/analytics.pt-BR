---
title: Visitas em única página
description: Um sinalizador que indica que a visita consistiu de uma única página.
translation-type: tm+mt
source-git-commit: e758c070f402113b6d8a9069437b53633974a3e9
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 81%

---


# Visitas em única página

*Esta página de ajuda descreve como &quot;Visitas em única página&quot; funciona como uma dimensão. Consulte a métrica[Visitas em única página](../metrics/single-page-visits.md)para obter mais informações.*

The &#39;Single page visits&#39; dimension reports the number of visits that consisted of a single unique [Page](page.md) dimension item. É o formato da dimensão da métrica [Visitas em única página](../metrics/single-page-visits.md).

Essa dimensão é utilizada mais frequentemente como um componente dentro da [segmentação](../segmentation/seg-home.md). Ela geralmente não é utilizada como uma dimensão em relatórios.

## Preencher esta dimensão com dados

Essa dimensão funciona imediatamente em todas as implementações. Se um conjunto de relatórios tiver dados, essa dimensão funcionará.

## itens de Dimension

The only dimension item is `"Enabled"`. Se uma visita consistir de uma única página, a ocorrência é definida como esse valor. Todas as outras ocorrências são omitidas deste relatório.
