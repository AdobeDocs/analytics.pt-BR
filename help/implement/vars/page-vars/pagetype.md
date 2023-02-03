---
title: pageType
description: Determine se a página atual é um erro 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 56%

---

# pageType

A variável `pageType` é um sinalizador usado para designar páginas de erro, como erros 404, no site. Se essa variável contiver a string `errorPage`, ele preenche as &quot;Páginas não encontradas&quot; [dimension](/help/components/dimensions/pages-not-found.md) e [métrica](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Não defina essa variável em páginas sem erros.

## Tipo de página usando o SDK da Web

O tipo de página é [mapeado para Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=pt-BR) no campo XDM `web.webPageDetails.isErrorPage`. Esse campo XDM é um booleano; defina como `true` para sinalizá-la como uma página de erro, ou `false` se não for uma página de erro. Adobe traduz automaticamente o booleano para o valor da string `errorPage` quando é enviado para um conjunto de relatórios do Analytics.

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
