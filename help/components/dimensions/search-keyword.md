---
title: Palavra-chave de pesquisa
description: A palavra-chave de pesquisa que o visitante usou para acessar seu site.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# Palavra-chave de pesquisa

A dimensão &#39;Palavra-chave de pesquisa&#39; relata as palavras-chave de pesquisa que os visitantes usam para acessar seu site.

>[!IMPORTANT] A maioria dos mecanismos de pesquisa não passa mais pela palavra-chave de pesquisa devido ao aumento das práticas de privacidade. Ocorrências nas quais a Adobe reconhece um mecanismo de pesquisa, mas não possui grupos de palavras-chave no valor da dimensão `"Keyword unavailable"`.

Uma quem indicou deve atender a ambas as seguintes opções para classificar como uma palavra-chave de pesquisa:

* O domínio de referência é reconhecido pela Adobe como um mecanismo [de](search-engine.md)pesquisa válido;
* Existe um parâmetro de string de query de palavra-chave no URL de referência. Se a string de query de palavra-chave existir, mas não contiver um valor, ela se agrupará sob o valor da dimensão `"Keyword unavailable"`.

Se você quiser distinguir a pesquisa paga e a pesquisa natural, a detecção [de pesquisa](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga é necessária. Várias dimensões estão disponíveis para palavras-chave de pesquisa:

* **Palavra-chave** de pesquisa: A palavra-chave de pesquisa usada para acessar seu site, independentemente de ser paga ou natural.
* **Palavra-chave de pesquisa - paga**: A palavra-chave de pesquisa usada para acessar seu site, que correspondia à detecção de pesquisa paga.
* **Palavra-chave de pesquisa - natural**: A palavra-chave de pesquisa usada para acessar seu site, que não correspondia à detecção de pesquisa paga.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor é baseado na [quem indicou](referrer.md) da ocorrência, que depende dos filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos. Verifique se a dimensão de quem indicou e os filtros internos de URL estão configurados corretamente.

## Valores de dimensão

Os valores de dimensão incluem palavras-chave de pesquisa usadas para acessar seu site. O valor da `"Unspecified"` dimensão é todo o tráfego não pesquisado.
