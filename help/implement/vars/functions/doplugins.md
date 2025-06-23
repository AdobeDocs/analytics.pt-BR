---
title: doPlugins
description: Configure a lógica antes de uma ocorrência ser compilada e enviada para a Adobe.
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 63%

---

# doPlugins

A variável `doPlugins` atua como uma &quot;última chamada&quot; para definir valores na implementação. É o local ideal para fazer chamadas para [Métodos de plug-in](../plugins/impl-plugins.md) e definir quaisquer variáveis desejadas antes do envio de uma solicitação de imagem. Se a [`usePlugins`](../config-vars/useplugins.md) estiver ativada, ela será executada automaticamente antes que qualquer tipo de solicitação de imagem seja compilada e enviada para a Adobe, incluindo:

* Todas as chamadas de exibição de página ([`t()`](t-method.md))
* Todas as chamadas de rastreamento de link ([`tl()`](tl-method.md)), incluindo links de download automático e links de saída

Use a variável `doPlugins` para chamar o código do plug-in e definir os valores finais da variável antes que uma solicitação de imagem seja compilada e enviada para a Adobe.

## Usar o código de retorno de chamada On Before Event Send usando a extensão Web SDK

Em vez de `doPlugins`, o Web SDK usa `onBeforeEventSend` com funcionalidade semelhante.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleção de dados], clique no botão **[!UICONTROL Editar em antes de enviar o código de retorno de chamada]**.
1. Coloque o código desejado no editor.

## Use o `onBeforeEventSend` para implementar manualmente o Web SDK

Em vez de `doPlugins`, o Web SDK usa `onBeforeEventSend` com funcionalidade semelhante. Consulte [Modificando eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do Web SDK para obter mais informações.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plug-ins que usam a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.doPlugins no AppMeasurement e no código personalizado do 

Defina a variável `s.doPlugins` em uma função que contenha o código desejado. A função é executada automaticamente quando você faz uma chamada de rastreamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
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
>As versões anteriores do AppMeasurement tinham um código de `doPlugins()` ligeiramente diferente. A Adobe recomenda usar o formato acima como prática recomendada.
