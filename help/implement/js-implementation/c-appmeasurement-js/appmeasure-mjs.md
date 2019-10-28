---
description: O AppMeasurement para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.
keywords: appmeasurement, implementação do Analytics, javascript, appmeasurement para javascript, inicialização, recuperar instância do appmeasurement, limpar vars, clearvars, utilitários do appmeasurement, instância do appmeasurement, benefícios do appmeasurement
seo-description: O AppMeasurement para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.
seo-title: Sobre o AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Sobre o AppMeasurement para JavaScript
topic: Desenvolvedor e implementação
uuid: dc71ad7a-92bd-40cd-8fab-707f6f8472e2
translation-type: ht
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Sobre o AppMeasurement para JavaScript

[!DNL AppMeasurement]O para JavaScript é uma nova biblioteca que oferece a mesma funcionalidade principal que s_code.js, mas é mais leve e rápida de usar em sites móveis e para desktop.

## O que você deve saber antes da implementação {#section_B8E7B39E8469468883BA0B41234F21C4}

A lista a seguir contém alterações que você deve compreender antes de passar para essa nova versão do [!DNL AppMeasurement]:

* Alguns plug-ins não são mais suportados. [Suporte a Plug-in do AppMeasurement para JavaScript](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).
* A biblioteca não é compatível com a seleção de conta dinâmica ([dynamicAccountList](/help/implement/js-implementation/c-variables/configuration-variables.md), [dynamicAccountMatch](/help/implement/js-implementation/c-variables/configuration-variables.md) e [dynamicAccountSelection](/help/implement/js-implementation/c-variables/configuration-variables.md)).

* O código da biblioteca e da página pode ser implantado dentro da tag `<head>`.
* Os módulos de Mídia e Integração são suportados com o uso do código atualizado do módulo que está no pacote de download [!DNL AppMeasurement] do JavaScript. O módulo Survey não é suportado.
* O código de página existente é compatível com a nova versão.
* A biblioteca oferece utilitários nativos para obter parâmetros de consulta, cookies de leitura e gravação e executar rastreamento de links avançado.

## Perguntas frequentes {#section_9BD41B08F7B54197B230937714B9357A}

Consulte as [Perguntas frequentes](../../../implement/faq.md#concept_9BBC230E01114318BE9C08724F2040D3) para informações sobre desempenho, rastreamento de vídeo, dispositivos móveis e muito mais.

## Processo de inicialização {#section_F6D5680F6D134B6AB1F01C6235860635}

Chame `s_gi()`, transmitindo a ID do conjunto de relatórios para inicializar uma instância de [!DNL AppMeasurement]:

```js
var s_account="INSERT-RSID-HERE"
var s=s_gi(s_account)
```

Uma nova`s_gi` [!DNL AppMeasurement] instância é criada quando é solicitado e se uma `s_account` instância de não existir para a  especificada. Caso contrário, a instância atual é retornada. Isso ajuda a evitar a criação de objetos duplicados na mesma conta.

## Recuperar uma instância AppMeasurement {#section_6F05C96DCAB24C8C9B4B91C5739630A6}

Em todo o código, chame a função global [s_gi()](../../../implement/js-implementation/function-s-gi.md#concept_50EE6629F61A478BB67781408FBA04BD) para recuperar uma instância [!DNL AppMeasurement] existente.

## Utilitários {#section_0F47694DD0214645A24C94AB6A4142A0}

JavaScript [!DNL AppMeasurement] fornece os seguintes utilitários incorporados:

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

