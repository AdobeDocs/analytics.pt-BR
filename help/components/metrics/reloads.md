---
title: Recargas
description: O número de vezes que a página foi recarregada.
feature: Metrics
exl-id: 9539a733-9e9f-48b3-b8ab-8d969de27f87
source-git-commit: c9b7c32adfb44a04ab792d12ca049106b3009710
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 21%

---

# Recargas

A [métrica](overview.md) de &quot;Recargas&quot; mostra o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento.

## Como essa métrica é calculada

Essa métrica conta o número de ocorrências nas quais a dimensão [Página](../dimensions/page.md) contém o mesmo valor da ocorrência anterior.

O conceito de recarregamento se aplica à dimensão Página, independentemente da dimensão usada nos relatórios. Por exemplo, se você usar [eVar1](../dimensions/evar.md) como uma dimensão e Recarregar como uma métrica, a tabela mostrará o número de vezes que cada valor de eVar foi apresentado durante um recarregamento (dois valores de página consecutivos). Ela não mostra o número de vezes que dois valores eVar1 consecutivos estavam presentes.
