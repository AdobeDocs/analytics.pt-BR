---
title: doPlugins
description: Configure a lógica antes de uma ocorrência ser compilada e enviada para a Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 66%

---

# doPlugins

A variável `doPlugins` atua como uma &quot;última chamada&quot; para definir valores na implementação. Se a [`usePlugins`](../config-vars/useplugins.md) estiver ativada, ela será executada automaticamente antes que qualquer tipo de solicitação de imagem seja compilada e enviada para a Adobe, incluindo:

* Todas as chamadas de exibição de página ([`t()`](t-method.md))
* Todas as chamadas de rastreamento de link ([`tl()`](tl-method.md)), incluindo links de download automático e links de saída

Use a variável `doPlugins` para chamar o código do plug-in e definir os valores finais da variável antes que uma solicitação de imagem seja compilada e enviada para a Adobe.

## Usar o código de retorno de chamada On Before Event Send usando a extensão SDK da Web

Em vez de `doPlugins`, o SDK da Web usa `onBeforeEventSend` com funcionalidade semelhante.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a [!UICONTROL Extensões] e clique na guia **[!UICONTROL Configurar]** botão em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], clique no link **[!UICONTROL Editar no antes do envio do evento código de retorno de chamada]** botão.
1. Coloque o código desejado no editor.

## Uso `onBeforeEventSend` implementação manual do SDK da Web

Em vez de `doPlugins`, o SDK da Web usa `onBeforeEventSend` com funcionalidade semelhante. Consulte [Modificação global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

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
