---
title: Idioma
description: A configuração de idioma preferencial no navegador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Idioma

A dimensão &#39;Idioma&#39; mostra os principais idiomas nos quais os visitantes preferem ver o conteúdo. Essa dimensão é valiosa quando você quer entender os idiomas preferenciais mais frequentes dos visitantes para auxiliar nos esforços de localização.

>[!NOTE]
>
>Essa dimensão não coleta o idioma do site. Se você quiser coletar o idioma do site em uma dimensão, a Adobe recomenda usar uma variável personalizada, como uma [eVar](evar.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho `Accept-Language` HTTP nas solicitações de imagem. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem nomes amigáveis dos idiomas preferidos dos visitantes. Examples include `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"`, and `"Spanish (Spain)"`. Se uma solicitação de imagem não contiver um idioma válido no cabeçalho HTTP, o item de dimensão será `"None"`.
