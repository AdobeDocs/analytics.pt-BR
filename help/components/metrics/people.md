---
title: Pessoas
description: O número de indivíduos únicos, geralmente com vários dispositivos.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7f9442d6be7930b9e040539dc683c62953aba342
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 53%

---

# Pessoas

Há duas versões da métrica &quot;Pessoas&quot;.

Para membros do [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=pt-BR) que não usam o [Cross-Device Analytics](../cda/overview.md), a métrica &quot;Pessoas&quot; é uma contagem derivada estatisticamente do número de pessoas representadas no relatório. É o número de IDs de visitante identificadas pelo Device Co-op, além do número de dispositivos que não são identificados pelo Co-op.

Em um conjunto de relatórios virtual [Cross-Device analytics](../cda/overview.md), a métrica &quot;Pessoas&quot; não é uma derivação estatística. Em vez disso, é a soma dos indivíduos identificados no relatório, mais o número de dispositivos que não são identificados como pertencentes a uma pessoa.

Se um visitante for identificado no meio da visita, ele poderá contar como 2 Pessoas até que [Reproduzir](/help/components/cda/replay.md) seja executado (1 pessoa não identificada e 1 pessoa identificada). Consulte [Dispositivos exclusivos](unique-devices.md) para obter mais informações.
