---
title: Páginas não encontradas (métricas)
description: O número de ocorrências que contém um erro.
feature: Metrics
exl-id: 71e138b5-69bb-41b0-852c-ca4af22be1f3
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 96%

---

# Páginas não encontradas

*Esta página de ajuda descreve como a dimensão &quot;Páginas não encontradas&quot; funciona como uma métrica. Consulte a dimensão [Páginas não encontradas](../dimensions/pages-not-found.md) para obter mais informações.*

A métrica “Páginas não encontradas” mostra o número de ocorrências em que a página continha um erro. Essa métrica é importante quando você quer ver quais páginas ou URLs contêm mensagens de erro (como 404), para que você possa determinar a causa do erro e corrigi-lo.

## Como essa métrica é calculada

Essa métrica conta todas as ocorrências em que a variável [`pageType`](/help/implement/vars/page-vars/pagetype.md) é igual ao valor de `"errorPage"`. É o equivalente métrico da dimensão [Páginas não encontradas](../dimensions/pages-not-found.md).
