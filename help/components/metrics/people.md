---
title: Pessoas
description: O número de indivíduos únicos, geralmente com vários dispositivos.
exl-id: 0136b843-2a1e-44d5-b5a6-e0fb03b7b995
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '160'
ht-degree: 100%

---

# Pessoas

Há duas versões da métrica &quot;Pessoas&quot;.

Para membros do [Device Co-op](https://experienceleague.adobe.com/docs/device-co-op/using/data/people.html?lang=pt-BR) que não usam o [Cross-Device Analytics](../cda/overview.md), a métrica &quot;Pessoas&quot; é uma contagem derivada estatisticamente do número de pessoas representadas no relatório. É o número de IDs de visitante identificadas pelo Device Co-op, além do número de dispositivos que não são identificados pelo Co-op.

Em um conjunto de relatórios virtual do [Cross-Device Analytics](../cda/overview.md), a métrica &quot;Pessoas&quot; é uma contagem direta de indivíduos únicos, em vez de uma derivação estatística. A definição de uma pessoa no CDA é baseada no Device Co-op, no Private Graph ou na compilação de campo, dependendo de como o CDA é configurado para o conjunto de relatórios base. Pessoas é a soma dos indivíduos que foram identificados no relatório, mais o número de dispositivos que não foram identificados como pertencendo a uma pessoa.
