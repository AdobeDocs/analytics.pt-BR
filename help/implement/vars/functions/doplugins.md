---
title: doPlugins
description: Configure a lógica antes de uma ocorrência ser compilada e enviada para a Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 100%

---


# doPlugins

A variável `doPlugins` atua como uma &quot;última chamada&quot; para definir valores na implementação. Se a [`usePlugins`](../config-vars/useplugins.md) estiver ativada, ela será executada automaticamente antes que qualquer tipo de solicitação de imagem seja compilada e enviada para a Adobe, incluindo:

* Todas as chamadas de exibição de página ([`t()`](t-method.md))
* Todas as chamadas de rastreamento de link ([`tl()`](tl-method.md)), incluindo links de download automático e links de saída

Use a variável `doPlugins` para chamar o código do plug-in e definir os valores finais da variável antes que uma solicitação de imagem seja compilada e enviada para a Adobe.

## Plug-ins no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.doPlugins no AppMeasurement e no código personalizado do Launch

Defina a variável `s.doPlugins` em uma função que contenha o código desejado. A função é executada automaticamente quando você faz uma chamada de rastreamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Defina uma função com a variável `doPlugins` somente uma vez na implementação. Se você definir a variável `doPlugins` mais de uma vez, apenas o código mais recente será usado.

## Exemplos

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>As versões anteriores do AppMeasurement tinham um código da `doPlugins()` ligeiramente diferente. A Adobe indica usar o formato acima como prática recomendada.
