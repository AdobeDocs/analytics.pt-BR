---
title: Navegador
description: O nome e a versão do navegador usado.
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 100%

---

# Navegador

A dimensão “Navegador” informa o nome e a versão do navegador que está enviando a ocorrência. Essa dimensão é útil para entender o que os visitantes usam com mais frequência. Ao testar novas versões do site, você pode executar esses testes nos navegadores principais nesta dimensão para maximizar os esforços de controle de qualidade.

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa interna da Adobe. O valor de pesquisa se baseia no cabeçalho HTTP `User-Agent` nas solicitações de imagem. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente.

## Itens de dimensão

Os itens de dimensão incluem os nomes e as versões do navegador usadas. Diferentes versões do mesmo navegador são itens de dimensão separados.

Alguns itens de dimensão contêm `"(unknown version)"` em vez do número de versão. Esse item de dimensão faz referência a uma versão recente do navegador que a Adobe não adicionou às tabelas de pesquisa. Como os navegadores são atualizados com frequência, o `"(unknown version)"` para um determinado navegador é comum e temporário. A Adobe normalmente atualiza as tabelas de pesquisa durante as versões de manutenção mensais.
