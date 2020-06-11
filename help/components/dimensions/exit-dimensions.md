---
title: Dimensões de saída
description: Dimensões de saída do Lista e seu uso.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---


# Dimensões de saída

*Esta página de ajuda descreve como as saídas funcionam como uma dimensão. Para obter informações sobre como as saídas funcionam como uma métrica, consulte a métrica[Saídas](../metrics/exits.md).*

As dimensões de saída registram o valor da última dimensão e o aplicam retroativamente a todas as ocorrências na visita. As dimensões de saída estão disponíveis para todas as variáveis com definição de caminho ativada em Variáveis [de](/help/admin/admin/c-traffic-variables/traffic-var.md) tráfego nas configurações do conjunto de relatórios.

## Preencher dimensões de saída com dados

Uma determinada dimensão de saída é baseada em sua variável de tráfego associada. Se a variável non-exit tiver dados, sua dimensão exit associada também contém dados. Nenhuma alteração de implementação é necessária para dimensões de saída se suas variáveis de tráfego contiverem dados.

## Valores de dimensão

Como as variáveis de saída normalmente são baseadas em strings personalizadas na sua implementação, sua organização determina quais são os valores de dimensão. Os valores em uma determinada dimensão de saída correspondem aos valores de dimensão em sua dimensão não de saída associada. Por exemplo, os valores de dimensão na dimensão &quot;Página de saída&quot; contêm valores de dimensão semelhantes na dimensão &quot;Página&quot;.
