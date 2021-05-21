---
title: Mecanismo de pesquisa
description: O mecanismo de pesquisa que o visitante utilizou para acessar seu site.
exl-id: 2815f1fa-d938-4d2b-b864-c4ed834f3ed3
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

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

## Itens de dimensão

Os itens de dimensão incluem mecanismos de pesquisa utilizados para acessar seu site. Os valores de exemplo incluem `"Google"`, `"Microsoft Bing"` e `"DuckDuckGo"`. O item de dimensão `"Unspecified"` é todo o tráfego que não é de pesquisa.
