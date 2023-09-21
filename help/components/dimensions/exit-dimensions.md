---
title: Dimensões de saída
description: Lista as dimensões de saída e o seu uso.
keywords: página de saída, seção do site de saída, servidor de saída, sair do Custom Insight
feature: Dimensions
exl-id: b2b1ee88-e5c3-44b5-8159-85ec53d20258
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 100%

---

# Dimensões de saída

*[Esta página de ajuda descreve como as saídas funcionam como uma dimensão](overview.md). Para obter informações sobre como as saídas funcionam como uma métrica, consulte a métrica [Saídas](../metrics/exits.md).*

As dimensões de saída registram o item da última dimensão e o aplicam retroativamente a todas ocorrências na visita. As dimensões de saída estão disponíveis para todas as variáveis com definição de caminho ativada em [Variáveis de tráfego](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Preencher dimensões de saída com dados

Uma determinada dimensão de saída é baseada em sua variável de tráfego associada. Se a variável de não saída tiver dados, sua dimensão de saída associada também terá dados. Nenhuma alteração na implementação é necessária para as dimensões de saída se suas variáveis de tráfego tiverem dados.

## Itens de dimensão

Como as variáveis de saída normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais são os itens de dimensão. Os valores de uma determinada dimensão de saída correspondem aos itens da sua dimensão de não saída associada. Por exemplo, os itens de dimensão na dimensão “Página de saída” contêm itens de dimensão semelhantes na dimensão “Página”.
