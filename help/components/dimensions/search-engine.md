---
title: Mecanismo de pesquisa
description: O mecanismo de pesquisa que o visitante utilizou para acessar seu site.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 91%

---


# Mecanismo de pesquisa

A dimensão “Mecanismo de pesquisa” informa os mecanismos de pesquisa que os visitantes utilizam para acessar seu site. Um referenciador deve atender às duas condições a seguir para ser classificado como um mecanismo de pesquisa:

* O domínio referenciador é reconhecido pela Adobe como um mecanismo de pesquisa válido;
* Existe um parâmetro de sequência de consulta de palavra-chave no URL de referência. O parâmetro da sequência de consulta pode estar em branco (como ocorre com vários mecanismos de pesquisa devido a práticas de privacidade).

Se você quiser distinguir a pesquisa paga da pesquisa natural, a [Detecção de pesquisa paga](/help/admin/admin/paid-search-detection/paid-search-detection.md) é necessária. Várias dimensões estão disponíveis para mecanismos de pesquisa:

* **Mecanismo de pesquisa**: o mecanismo de pesquisa utilizado para acessar seu site, independentemente de ser pago ou natural.
* **Mecanismo de pesquisa - pago**: o mecanismo de pesquisa utilizado para acessar seu site que correspondeu à detecção de pesquisa paga.
* **Mecanismo de pesquisa - natural**: o mecanismo de pesquisa utilizado para acessar o site que não correspondeu à detecção de pesquisa paga.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor se baseia no [referenciador](referrer.md) da ocorrência, que depende dos [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). Verifique se a dimensão do referenciador e os filtros de URL internos estão configurados corretamente.

## itens de Dimension

Os itens de Dimension incluem mecanismos de pesquisa usados para acessar seu site. Os valores de exemplo incluem `"Google"`, `"Microsoft Bing"` e `"DuckDuckGo"`. The `"Unspecified"` dimension item is all non-search traffic.
