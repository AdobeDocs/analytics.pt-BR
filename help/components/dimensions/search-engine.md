---
title: Mecanismo de Pesquisa
description: O mecanismo de pesquisa que o visitante usou para acessar seu site.
translation-type: tm+mt
source-git-commit: 1869d69566d26aa7d99c520efc2e835901439d48
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Mecanismo de Pesquisa

A dimensão &#39;Mecanismo de pesquisa&#39; relata os mecanismos de pesquisa que os visitantes usam para acessar seu site. Uma quem indicou deve atender a ambas as condições a seguir para classificar como um mecanismo de pesquisa:

* O domínio de referência é reconhecido pela Adobe como um mecanismo de pesquisa válido;
* Existe um parâmetro de string de query de palavra-chave no URL de referência. O parâmetro da string de query pode estar em branco (como ocorre com vários mecanismos de pesquisa devido a práticas de privacidade).

Se você quiser distinguir a pesquisa paga e a pesquisa natural, a detecção [de pesquisa](/help/admin/admin/paid-search-detection/paid-search-detection.md) paga é necessária. Várias dimensões estão disponíveis para mecanismos de pesquisa:

* **Mecanismo** de pesquisa: O mecanismo de pesquisa usado para acessar seu site, independentemente de ser pago ou natural.
* **Mecanismo de pesquisa - pago**: O mecanismo de pesquisa usado para acessar seu site, que correspondia à detecção de pesquisa paga.
* **Mecanismo de busca - natural**: O mecanismo de pesquisa usado para acessar o site, que não correspondia à detecção de pesquisa paga.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor é baseado na [quem indicou](referrer.md) da ocorrência, que depende dos filtros [de URL](/help/admin/admin/internal-url-filter-admin.md)internos. Verifique se a dimensão de quem indicou e os filtros internos de URL estão configurados corretamente.

## Valores de dimensão

Os valores de dimensão incluem mecanismos de pesquisa usados para acessar seu site. Os valores de exemplo incluem `"Google"`, `"Microsoft Bing"`e `"DuckDuckGo"`. O valor da `"Unspecified"` dimensão é todo o tráfego não pesquisado.
