---
title: Dimensões de saída
description: Lista as dimensões de saída e o seu uso.
keywords: exit page, exit site section, exit server, exit custom insight
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---


# Dimensões de saída

*Esta página de ajuda descreve como as saídas funcionam como uma dimensão. Para obter informações sobre como as saídas funcionam como uma métrica, consulte a métrica [Saídas](../metrics/exits.md).*

As dimensões de saída registram o item da última dimensão e o aplicam retroativamente a todas ocorrências na visita. As dimensões de saída estão disponíveis para todas as variáveis com definição de caminho ativada em [Variáveis de tráfego](/help/admin/admin/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Preencher dimensões de saída com dados

Uma determinada dimensão de saída é baseada em sua variável de tráfego associada. Se a variável de não saída tiver dados, sua dimensão de saída associada também terá dados. Nenhuma alteração na implementação é necessária para as dimensões de saída se suas variáveis de tráfego tiverem dados.

## Itens de dimensão

Como as variáveis de saída normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais são os itens de dimensão. Os valores de uma determinada dimensão de saída correspondem aos itens da sua dimensão de não saída associada. Por exemplo, os itens de dimensão na dimensão “Página de saída” contêm itens de dimensão semelhantes na dimensão “Página”.
