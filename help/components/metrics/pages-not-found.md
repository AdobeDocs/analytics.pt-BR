---
title: Páginas não encontradas
description: O número de ocorrências que contém um erro.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 5%

---


# Páginas não encontradas

*Esta página de ajuda descreve como &quot;Páginas não encontradas&quot; funciona como uma métrica. Consulte a dimensão[Páginas não encontradas](../dimensions/pages-not-found.md)para obter mais informações.*

A métrica &#39;Páginas não encontradas&#39; mostra o número de ocorrências nas quais a página continha um erro. Essa métrica é importante quando você deseja ver quais páginas ou URLs contêm mensagens de erro (como 404), para que você possa determinar a causa do erro e corrigi-lo.

## Como essa métrica é calculada

Essa métrica conta todas as ocorrências em que a [`pageType`](/help/implement/vars/page-vars/pagetype.md) variável é igual ao valor de `"errorPage"`. É o equivalente métrico da dimensão [Páginas não encontradas](../dimensions/pages-not-found.md) .