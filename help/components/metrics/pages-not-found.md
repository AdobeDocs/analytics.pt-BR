---
title: Páginas não encontradas (métricas)
description: O número de ocorrências que contém um erro.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: a15d2b596c1e8b70e91efb49dd607fdbb0ceec3c
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 35%

---

# Páginas não encontradas

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma métrica. Consulte a página de dimensão [Páginas não encontradas](../dimensions/pages-not-found.md) para obter mais informações sobre como ela funciona como uma dimensão.*

A [métrica](overview.md) de &quot;Páginas não encontradas&quot; mostra o número de ocorrências em que uma dimensão foi definida ou mantida no momento em que um visitante encontrou um erro. Essa métrica é importante quando você quer ver quais páginas ou URLs contêm mensagens de erro (como 404). Em seguida, você pode transmitir essas informações para a equipe de desenvolvimento da Web, que pode determinar a causa do erro e corrigi-lo.

## Como essa métrica é calculada

Essa métrica conta todas as ocorrências em que a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md) é igual ao valor de `"errorPage"`. É o equivalente métrico da dimensão [Páginas não encontradas](../dimensions/pages-not-found.md).
