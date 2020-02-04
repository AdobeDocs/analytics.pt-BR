---
title: pageType
description: Determine se a página atual é um erro 404.
translation-type: tm+mt
source-git-commit: 751d19227d74d66f3ce57888132514cf8bd6f7fc

---


# pageType

A `pageType` variável é um sinalizador usado para designar páginas de erro no site, como erros 404. Se essa variável contiver a string, ela preencherá a dimensão &quot;Páginas não encontradas&quot;. `errorPage`

> [!IMPORTANT] Não defina essa variável em páginas sem erros.

## Tipo de página no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.pageType no AppMeasurement e Iniciar editor de código personalizado

A `s.pageType` variável é uma string na qual o valor `errorPage` é seu único valor válido. Defina essa variável como esse valor em qualquer página de erro do site, como em 404 páginas.

```js
s.pageType = "errorPage";
```

> [!TIP] Use uma eVar para coletar o código de erro para obter mais informações sobre os erros específicos que os visitantes encontram no site.
