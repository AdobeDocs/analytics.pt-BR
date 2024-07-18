---
title: Idioma
description: A configuração de idioma preferencial do navegador.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 91%

---

# Idioma

A [dimensão](overview.md) de &quot;Idioma&quot; mostra os principais idiomas em que os visitantes preferem ver o conteúdo. Essa dimensão é importante quando você quer entender os idiomas preferenciais mais frequentes dos visitantes para auxiliar nas tarefas de localização.

>[!NOTE]
>
>Essa dimensão não coleta o idioma do site. Se você quiser coletar o idioma do site em uma dimensão, a Adobe recomenda usar uma variável personalizada, como uma [eVar](evar.md).

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `Accept-Language` nas solicitações de imagem. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem nomes amigáveis nos idiomas de preferência dos visitantes. Os exemplos incluem `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` e `"Spanish (Spain)"`. Se uma solicitação de imagem não contiver um idioma válido no cabeçalho HTTP, o item de dimensão será `"None"`.
