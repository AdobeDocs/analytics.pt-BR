---
description: O número de vezes que um determinado valor é capturado como o último em uma visita. Saídas podem ocorrer somente uma vez por visita.
title: Saídas
topic: Metrics
uuid: cd5436ef-65d3-431b-a24f-aceff8542c50
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# Saídas

O número de vezes que um determinado valor é capturado como o último em uma visita. Saídas podem ocorrer somente uma vez por visita.

As páginas de saída possuem um escopo de interrupção de visita, o que significa que elas persistem em todos os hits de uma visita. Ver [Contêineres de interrupção e segmentação](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html) para obter mais informações.

Quando aplicadas a uma dimensão, as Saídas são consideradas no último valor de uma visita, o que pode ocorrer em qualquer ocorrência durante a visita. Se não existir um valor na última ocorrência, a Saída é atribuída ao valor mais recente.

Se uma saída ocorrer fora do intervalo de relatório para uma visita do intervalo de relatório, ela será incluída contanto que não esteja no limite de um mês (no conjunto de dados).
