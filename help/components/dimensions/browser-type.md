---
title: Tipo de Navegador
description: A organização que fez o navegador.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 3%

---


# Tipo de Navegador

A dimensão &#39;Tipo de navegador&#39; lista organizações que fizeram o navegador que o visitante usa. Essa dimensão é útil quando você deseja ver quais navegadores principais os visitantes usam. Ele fornece valor sobre a dimensão &quot;Navegadores&quot;, na medida em que não lista versões diferentes do mesmo navegador como itens de dimensão separados.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho `User-Agent` HTTP nas solicitações de imagem. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem organizações que fazem navegadores. Os itens de dimensão comuns incluem `"Google"` (os criadores de [!DNL Chrome]), `"Apple"` (os criadores de [!DNL Safari]), `"Microsoft"` (os criadores de [!DNL Edge]) e `"Mozilla"` (os criadores de [!DNL Firefox]).
