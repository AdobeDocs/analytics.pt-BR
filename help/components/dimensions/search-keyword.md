---
title: Palavra-chave de pesquisa
description: A palavra-chave de pesquisa que o visitante utilizou para acessar seu site.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '250'
ht-degree: 100%

---


# Palavra-chave de pesquisa

A dimensão “Palavra-chave de pesquisa” informa as palavras-chave de pesquisa que os visitantes utilizam para acessar seu site.

>[!IMPORTANT]
>
>A maioria dos mecanismos de pesquisa não passa mais a palavra-chave de pesquisa devido ao aumento das práticas de privacidade. Ocorrências em que a Adobe reconhece um mecanismo de pesquisa, mas falta um grupo de palavras-chave no item de dimensão `"Keyword unavailable"`.

Um referenciador deve atender aos dois itens a seguir para se classificar como uma palavra-chave de pesquisa:

* O domínio referenciador é reconhecido pela Adobe como um [mecanismo de pesquisa](search-engine.md) válido;
* Existe um parâmetro de sequência de consulta de palavra-chave no URL de referência. Se uma sequência de consulta por palavras-chave existir mas não tiver um valor, ela se agrupará sob o item de dimensão `"Keyword unavailable"`.

Se você quiser distinguir a pesquisa paga da pesquisa natural, a [Detecção de pesquisa paga](/help/admin/admin/paid-search-detection/paid-search-detection.md) é necessária. Várias dimensões estão disponíveis para palavras-chave de pesquisa:

* **Palavra-chave de pesquisa**: a palavra-chave de pesquisa utilizada para acessar seu site, independentemente de ser paga ou comum.
* **Palavra-chave de pesquisa - paga**: a palavra-chave de pesquisa usada para acessar seu site que corresponde à detecção de pesquisa paga.
* **Palavra-chave de pesquisa - comum**: a palavra-chave de pesquisa utilizada para acessar seu site que não corresponde à detecção de pesquisa paga.

## Preencher esta dimensão com dados

Essa dimensão faz referência a várias tabelas de pesquisa internas da Adobe. Cada valor se baseia no [referenciador](referrer.md) da ocorrência, que depende dos [Filtros de URL internos](/help/admin/admin/internal-url-filter-admin.md). Verifique se a dimensão do referenciador e os filtros de URL internos estão configurados corretamente.

## Itens de dimensão

Os itens de dimensão incluem palavras-chave de pesquisa utilizadas para acessar seu site. O item de dimensão `"Unspecified"` é todo o tráfego que não é de pesquisa.
