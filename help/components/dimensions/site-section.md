---
title: Seção do site
description: O nome da seção do site.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Seção do site

A dimensão &quot;Seção do site&quot; lista os nomes das seções do site. Para sites grandes, é útil agrupar páginas em seções. Essa dimensão é útil para ver as seções de site com melhor desempenho ou mais exibidas.

Essa dimensão está relacionada às dimensões [Página](page.md) e [Servidor](server.md) . A página é mais granular, o Servidor é menos granular e a seção Site fica entre os dois.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`ch` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a [`channel`](/help/implement/vars/page-vars/channel.md) variável.

## Valores de dimensão

Os valores de dimensão incluem os nomes das seções do site. Sua organização determina quais valores de dimensão específicos você deseja usar. Qualquer que seja o método usado, verifique se ele é consistente e se você o registra em um documento [de design de](/help/implement/prepare/solution-design.md)solução.
