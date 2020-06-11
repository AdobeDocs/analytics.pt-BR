---
title: Dimensões de entrada
description: Lista dimensões de entrada e seu uso.
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# Dimensões de entrada

*Esta página de ajuda descreve como as entradas funcionam como uma dimensão. Para obter informações sobre como as entradas funcionam como uma métrica, consulte a métrica[Entradas](../metrics/entries.md).*

As dimensões de entrada são baseadas em visitas. Eles registram o primeiro valor de dimensão e o mantêm por toda a duração dessa visita. As dimensões de entrada estão disponíveis para todas as variáveis com definição de caminho ativada em Variáveis [de](/help/admin/admin/c-traffic-variables/traffic-var.md) tráfego nas configurações do conjunto de relatórios.

## Preencher dimensões de entrada com dados

Uma determinada dimensão de entrada se baseia em sua variável de tráfego associada. Se a variável de não entrada tiver dados, sua dimensão de entrada associada também conterá dados. Nenhuma alteração de implementação é necessária para dimensões de entrada se suas variáveis de tráfego contiverem dados.

## Valores de dimensão

Como as variáveis de entrada normalmente se baseiam em strings personalizadas na sua implementação, sua organização determina quais são os valores de dimensão. Os valores em uma determinada dimensão de entrada correspondem aos valores de dimensão em sua dimensão de não entrada associada. Por exemplo, os valores de dimensão na dimensão &#39;Página de entrada&#39; contêm valores de dimensão semelhantes na dimensão &#39;Página&#39;.

## Página inicial

A dimensão &quot;original da página de entrada&quot; opera de forma diferente das outras dimensões de entrada. Em vez de preservar a página de entrada de uma determinada visita, ela preserva a primeira página de entrada durante toda a vida do cookie do visitante. Por exemplo, se você navegar `https://example.com/page4` para sua primeira visita ao site, em seguida, um ano depois será iniciado, `https://example.com/store`a dimensão &quot;Original da página de entrada&quot; será lista `https://example.com/page4` como o valor da dimensão.
