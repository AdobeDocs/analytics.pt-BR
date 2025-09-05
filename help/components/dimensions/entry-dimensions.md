---
title: Dimensões de entrada
description: Lista dimensões de entrada e seu uso.
keywords: página de entrada, seção de entrada no site, servidor de entrada, insight personalizado de entrada
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 75%

---

# Dimensões de entrada

*Esta página de ajuda descreve como as entradas funcionam como uma [dimensão](overview.md). Para obter informações sobre como as entradas funcionam como uma métrica, consulte a [métrica Entradas](../metrics/entries.md).*

As dimensões de entrada são [baseadas em visitas](../metrics/visits.md). Elas registram o primeiro item de dimensão e o mantêm por toda a duração dessa visita. As dimensões de entrada estão disponíveis para todas as variáveis com definição de caminho habilitada em [Variáveis de tráfego](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

>[!TIP]
>Se quiser ver dados com base na primeira ocorrência de uma visita em vez do primeiro valor visto em uma visita, você pode usar um [segmento](/help/components/segmentation/seg-overview.md). Use um contêiner de ocorrências em que [Profundidade da ocorrência](hit-depth.md) seja igual a 1 e use esse segmento com a variável desejada.

## Preencher dimensões de entrada com dados

Uma determinada entrada [dimension](overview.md) é baseada em sua variável de tráfego associada. Se a variável de não entrada tiver dados, sua dimensão de entrada associada também conterá dados. Nenhuma alteração de implementação é necessária para dimensões de entrada se suas variáveis de tráfego contiverem dados.

## Itens de dimensão

Como as variáveis de entrada normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais são os itens de dimensão. Os valores em uma determinada dimensão de entrada correspondem aos itens de dimensão em sua dimensão de não entrada associada. Por exemplo, os itens de dimensão na dimensão “Página de entrada” contêm itens de dimensão semelhantes na dimensão “Página”.

## Página de entrada original

A dimensão &quot;Página de entrada original&quot; opera de forma diferente das outras dimensões de entrada. Em vez de preservar a página de entrada de uma determinada visita, ela preserva a primeira página de entrada durante toda a vida do cookie do visitante. Por exemplo, se você acessar `https://example.com/page4` como sua primeira visita ao site e, um ano depois, `https://example.com/store` a dimensão “Página de entrada original” lista `https://example.com/page4` como o item de dimensão.
