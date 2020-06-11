---
title: Navegador
description: O nome e a versão do navegador usado.
translation-type: tm+mt
source-git-commit: 4a7b3a00bdbf557c219de530e3e692c2b2db4a84
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 1%

---


# Navegador

A dimensão &#39;Navegador&#39; relata o nome e a versão do navegador que está enviando a ocorrência. Essa dimensão é útil para entender o que os visitantes usam com mais frequência. Ao testar novas versões do site, você pode executar esses testes nos navegadores principais nesta dimensão para maximizar os esforços de controle de qualidade.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho `User-Agent` HTTP nas solicitações de imagem. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente.

## Valores de dimensão

Os valores de dimensão incluem os nomes e as versões do navegador usadas. Diferentes versões do mesmo navegador são valores de dimensão separados.

Alguns valores de dimensão contêm `"(unknown version)"` em vez de seu número de versão. Esse valor de dimensão faz referência a uma versão recente do navegador que a Adobe não adicionou às tabelas de pesquisa. Como os navegadores são atualizados com frequência, o `"(unknown version)"` para um determinado navegador é comum e temporário. A Adobe normalmente atualiza as tabelas de pesquisa durante as versões de manutenção mensais.
