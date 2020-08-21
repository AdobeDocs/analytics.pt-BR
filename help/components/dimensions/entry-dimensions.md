---
title: Dimensões de entrada
description: Lista dimensões de entrada e seu uso.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# Dimensões de entrada

*Esta página de ajuda descreve como as entradas funcionam como uma dimensão. Para obter informações sobre como as entradas funcionam como uma métrica, consulte a[métrica Entradas](../metrics/entries.md).*

As dimensões de entrada se baseiam em visitas. Eles registram o primeiro item de dimensão e o mantêm por toda a duração dessa visita. As dimensões de entrada estão disponíveis para todas as variáveis com definição de caminho ativada em [Variáveis de tráfego](/help/admin/admin/c-traffic-variables/traffic-var.md) nas configurações do conjunto de relatórios.

## Preencher dimensões de entrada com dados

Uma determinada dimensão de entrada se baseia em sua variável de tráfego associada. Se a variável de não entrada tiver dados, sua dimensão de entrada associada também conterá dados. Nenhuma alteração de implementação é necessária para dimensões de entrada se suas variáveis de tráfego contiverem dados.

## itens de Dimension

Como as variáveis de entrada normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais itens de dimensão são. Os valores em uma determinada dimensão de entrada correspondem aos itens de dimensão em sua dimensão de não entrada associada. Por exemplo, os itens de dimensão na dimensão &#39;Página de entrada&#39; contêm itens de dimensão semelhantes na dimensão &#39;Página&#39;.

## Página de entrada original

A dimensão &quot;Página de entrada original&quot; opera de forma diferente das outras dimensões de entrada. Em vez de preservar a página de entrada de uma determinada visita, ela preserva a primeira página de entrada durante toda a vida do cookie do visitante. For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
