---
title: pageType
description: Determine se a página atual é um erro 404.
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 75%

---

# pageType

A variável `pageType` é um sinalizador usado para designar páginas de erro, como erros 404, no site. Se essa variável contiver a string `errorPage`, ela preencherá a [dimensão](/help/components/dimensions/pages-not-found.md) &quot;Páginas não encontradas&quot; e [métrica](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Não defina essa variável em páginas sem erros.

## Tipo de página usando o SDK da Web

O canal é mapeado para as seguintes variáveis:

* [Objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage` - este campo XDM é um booleano; defina-o como `true` para sinalizá-lo como uma página de erro, ou `false` se não for uma página de erro.
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` - este campo de objeto de dados é uma cadeia de caracteres; defina-o como `"errorPage"` para sinalizá-lo como tal.

## Tipo de página usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.pageType no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.pageType` é uma string na qual o valor `errorPage` é seu único valor válido. Use esse valor para essa variável em qualquer página de erro, como páginas 404, do seu site.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Use uma eVar para coletar o código de erro e obter mais informações sobre os erros específicos que os visitantes encontram no site.
