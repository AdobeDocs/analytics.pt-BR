---
description: O AppMeasurement para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.
keywords: appmeasurement; Implementação do Analytics; javascript; appmeasurement para javascript; initialização; recuperar instância do appmeasurement; clear vars; clearvars; utilitários de appmeasurement; instância do appmeasurement; benefícios do appmeasurement
seo-description: O AppMeasurement para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.
seo-title: Sobre o AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Sobre o AppMeasurement para JavaScript
topic: Desenvolvedor e implementação
uuid: dc 71 ad 7 a -92 bd -40 cd -8 fab -707 f 6 f 8472 e 2
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Sobre o AppMeasurement para JavaScript

[!DNL AppMeasurement]O para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.

## O que você deve saber antes da implementação {#section_B8E7B39E8469468883BA0B41234F21C4}

The following list contains changes you need to understand before switching to this new [!DNL AppMeasurement] version:

* Alguns plug-ins não são mais suportados. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* The library does not support dynamic account selection ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md), and [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* The library and page code can be deployed inside the `<head>` tag.
* The Media and Integrate modules are supported using updated module code that is in the JavaScript [!DNL AppMeasurement] download package. O módulo Survey não é suportado.
* O código de página existente é compatível com a nova versão.
* A biblioteca oferece utilitários nativos para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.

## Perguntas frequentes {#section_9BD41B08F7B54197B230937714B9357A}

See the [FAQ](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) for information about performance, video tracking, mobile, and more.

## Processo de inicialização {#section_F6D5680F6D134B6AB1F01C6235860635}

Call `s_gi()`, passing the report suite ID to initialize an [!DNL AppMeasurement] instance:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

When `s_gi` is called, if an [!DNL AppMeasurement] instance does not exist for the specified `s_account`, a new instance is created. Caso contrário, a instância atual é retornada. Isso ajuda a evitar a criação de objetos duplicados na mesma conta.

## Recuperar uma instância AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Throughout your code, call the global [s_gi() function](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) to retrieve an existing [!DNL AppMeasurement] instance.

## Utilitários {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] provides the following built-in utilities:

* [Util.cookieRead](../../../implement/js-implementation/util-cookieread.md#concept_33BD774A90504F2C8094DDC16D47440D)
* [Util.cookieWrite](../../../implement/js-implementation/util-cookiewrite.md#concept_9BE4F7D9CDAE4445B9AF3212BC7E61F2)
* [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

## Clear Vars {#section_597C411E7EDB42BC9A6A0508C9D57147}

Um novo método `clearVars` está disponível para apagar os seguintes valores do objeto da instância:

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Por exemplo:

```js
s.clearVars()
```

## Benefícios {#section_091E5A28E89E438E8A54A95F55165743}

* De 3 a 7 vezes mais rápida que o código H.25.
* Somente 21k descompactado e 8k compactado por gzip (o código H.25 pesa 33k descompactado e 13k compactado por gzip).
* Suporte nativo para vários plug-ins comuns ().
* Pequeno e rápido o suficiente para ser usado em sites móveis e robusto o suficiente para ser usado na Web completa para desktop, permitindo que você utilize uma única biblioteca em todos os ambientes da Web.

