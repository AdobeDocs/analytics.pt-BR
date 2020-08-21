---
title: pageType
description: Determine se a página atual é um erro 404.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '135'
ht-degree: 100%

---


# pageType

A variável `pageType` é um sinalizador usado para designar páginas de erro, como erros 404, no site. Se essa variável contiver a string `errorPage`, ela preencherá a dimensão &quot;Páginas não encontradas&quot;.

>[!IMPORTANT]
>
>Não defina essa variável em páginas sem erros.

## Tipo de página no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.pageType no AppMeasurement e no editor de código personalizado do Launch

A variável `s.pageType` é uma string na qual o valor `errorPage` é seu único valor válido. Use esse valor para essa variável em qualquer página de erro, como páginas 404, do seu site.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Use uma eVar para coletar o código de erro e obter mais informações sobre os erros específicos que os visitantes encontram no site.
