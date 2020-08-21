---
title: Páginas não encontradas
description: O número de ocorrências que contém um erro.
translation-type: ht
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---


# Páginas não encontradas

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma métrica. Consulte a dimensão[Páginas não encontradas](../dimensions/pages-not-found.md)para obter mais informações.*

A métrica “Páginas não encontradas” mostra o número de ocorrências em que a página continha um erro. Essa métrica é importante quando você quer ver quais páginas ou URLs contêm mensagens de erro (como 404), para que você possa determinar a causa do erro e corrigi-lo.

## Como essa métrica é calculada

Essa métrica conta todas as ocorrências em que a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md) é igual ao valor de `"errorPage"`. É o equivalente métrico da dimensão [Páginas não encontradas](../dimensions/pages-not-found.md).