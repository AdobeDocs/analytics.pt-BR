---
title: doPlugins
description: Configure a lógica antes de uma ocorrência ser compilada e enviada para a Adobe.
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# doPlugins

A `doPlugins` variável atua como uma &quot;última chamada&quot; para definir valores na sua implementação. Se `usePlugins` estiver `true`, ele será executado automaticamente antes que qualquer tipo de solicitação de imagem seja compilada e enviada para a Adobe, incluindo:

* Todas as chamadas de exibição de página (`t`)
* Todas as chamadas de rastreamento de link (`tl`), incluindo links de download automáticos e links de saída

Use a `doPlugins` variável para chamar o código do plug-in e definir os valores finais da variável antes que uma solicitação de imagem seja compilada e enviada para a Adobe.

## Plug-ins no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.doPlugins no código personalizado do AppMeasurement e do Launch

Defina a `s.doPlugins` variável para uma função que contenha o código desejado. A função é executada automaticamente quando você faz uma chamada de rastreamento.

```js
s.doPlugins = function() {/* Desired code */};
```

> [!NOTE] Defina uma função para a `doPlugins` variável somente uma vez na implementação. Se você definir a `doPlugins` variável mais de uma vez, somente o código mais recente será usado.

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

> [!NOTE] As versões anteriores do AppMeasurement tinham um `doPlugins()` código ligeiramente diferente. A Adobe recomenda usar o formato acima como prática recomendada.
