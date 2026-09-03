---
title: doPlugins
description: Configure a lógica antes de uma ocorrência ser compilada e enviada para a Adobe.
feature: Appmeasurement Implementation
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/ZS7Kpl1vxzJIGLzk1AkZBNEpPdGd-8NQq1-HW-zqDck'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 326
ht-degree: 61%

---

# doPlugins

A variável `doPlugins` atua como uma &quot;última chamada&quot; para definir valores na implementação. É o local ideal para fazer chamadas para [Métodos de plug-in](../plugins/impl-plugins.md) e definir quaisquer variáveis desejadas antes do envio de uma solicitação de imagem. Se a [`usePlugins`](../config-vars/useplugins.md) estiver habilitada, ela será executada automaticamente antes que qualquer tipo de solicitação de imagem seja compilada e enviada para a Adobe, incluindo:

* Todas as chamadas de exibição de página ([`t()`](t-method.md))
* Todas as chamadas de rastreamento de link ([`tl()`](tl-method.md)), incluindo links de download automático e links de saída

Use a variável `doPlugins` para chamar o código do plug-in e definir os valores finais da variável antes que uma solicitação de imagem seja compilada e enviada para a Adobe.

## Usar o código de retorno de chamada On Before Event Send usando a extensão Web SDK

Em vez de `doPlugins`, o Web SDK usa `onBeforeEventSend` com funcionalidade semelhante.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
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
