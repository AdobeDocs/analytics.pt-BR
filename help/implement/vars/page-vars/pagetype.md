---
title: pageType
description: Determine se a página atual é um erro 404.
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 83%

---

# pageType

A variável `pageType` é um sinalizador usado para designar páginas de erro, como erros 404, no site. Se essa variável contiver a string `errorPage`, ela preencherá a dimensão &quot;Páginas não encontradas&quot;.

>[!IMPORTANT]
>
>Não defina essa variável em páginas sem erros.

## Tipo de página usando tags no Adobe Experience Platform

Não há um campo dedicado na interface do usuário da coleta de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.pageType no AppMeasurement e no editor de código personalizado do 

A variável `s.pageType` é uma string na qual o valor `errorPage` é seu único valor válido. Use esse valor para essa variável em qualquer página de erro, como páginas 404, do seu site.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Use uma eVar para coletar o código de erro e obter mais informações sobre os erros específicos que os visitantes encontram no site.
