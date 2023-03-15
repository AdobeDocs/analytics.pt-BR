---
title: registerPreTrackCallback
description: Crie funções de retorno de chamada após enviar uma ocorrência para a Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 61%

---

# registerPreTrackCallback

A variável `registerPreTrackCallback` permite que sua organização execute uma função JavaScript após um URL de solicitação de imagem ser compilado, mas antes de ser enviado. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement a um parceiro ou infraestrutura interna.

>[!WARNING]
>
>Não chame nenhuma função de rastreamento como [`t()`](t-method.md) ou [`tl()`](tl-method.md) dentro da variável [`registerPostTrackCallback`](registerposttrackcallback.md). As funções de rastreamento nesta variável causam um loop infinito de solicitações de imagem!

Cada vez que chama a variável `registerPreTrackCallback`, você faz com que essa função seja executada sempre que um URL de solicitação de imagem for compilado. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

>[!NOTE]
>
>O tempo e a ordem das funções disparadas entre `registerPreTrackCallback` e `registerPostTrackCallback` não são garantidos. Evite dependências entre essas duas funções.

## Pré-rastrear retorno de chamada usando a extensão SDK da Web

O SDK da Web não tem a capacidade de interceptar uma função após a compilação de dados, mas antes de serem enviados para o Adobe. No entanto, você pode usar `onBeforeEventSend` para registrar uma função a ser executada antes do envio dos dados.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a [!UICONTROL Extensões] e clique na guia **[!UICONTROL Configurar]** botão em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], clique no link **[!UICONTROL Editar no antes do envio do evento código de retorno de chamada]** botão.
1. Coloque o código desejado no editor.

## Pré-rastrear retorno de chamada implementando manualmente o SDK da Web

O SDK da Web não tem a capacidade de interceptar uma função após a compilação de dados, mas antes de serem enviados para o Adobe. No entanto, você pode usar `onBeforeEventSend` para registrar uma função a ser executada antes do envio dos dados, semelhante a `doPlugins`. Consulte [Modificação global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Pré-rastrear retorno de chamada usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.registerPreTrackCallback no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.registerPreTrackCallback` é uma função que utiliza uma função como seu único argumento. A função aninhada é executada antes do envio de uma solicitação de imagem.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se você quiser usar o URL da solicitação de imagem em seu código, consulte o argumento em string de `requestUrl` na função aninhada. Você pode analisar a variável `requestUrl` para usá-la como desejar; o ajuste dessa variável não afeta a coleta de dados.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

É possível incluir argumentos adicionais na função `s.registerPreTrackCallback`, que podem ser usados na função aninhada:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>Definir variáveis de página ou alterar a string `requestUrl` dentro dessa função **não** afeta a solicitação de imagem enviada logo após essa chamada de função. Em vez disso, use a variável [`doPlugins()`](doplugins.md).
