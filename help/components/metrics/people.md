---
title: Pessoas
description: O número de indivíduos únicos, geralmente com vários dispositivos.
feature: Metrics
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 100%

---

# Pessoas

Há duas versões da métrica &quot;Pessoas&quot;.

Para membros do [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=pt-BR) que não usam o [Cross-Device Analytics](../cda/overview.md), a métrica &quot;Pessoas&quot; é uma contagem derivada estatisticamente do número de pessoas representadas no relatório. É o número de IDs de visitante identificadas pelo Device Co-op, além do número de dispositivos que não são identificados pelo Co-op.

Em um conjunto de relatórios virtual de [Análise entre dispositivos](../cda/overview.md), a métrica &quot;Pessoas&quot; não é uma derivação estatística. &quot;Pessoas&quot; é a soma dos indivíduos que foram identificados no relatório, mais o número de dispositivos que não foram identificados como pertencendo a uma pessoa.

Se um visitante for identificado no meio da visita, ele poderá contar como 2 Pessoas (1 pessoa não identificada e 1 pessoa identificada). [A repetição](/help/components/cda/replay.md) reduz essa dupla contagem, dependendo da janela de relatório, da frequência de repetição e da taxa de sucesso. Consulte [Dispositivos exclusivos](unique-devices.md) para obter mais informações.
