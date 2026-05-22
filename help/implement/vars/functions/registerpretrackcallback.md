---
title: registerPreTrackCallback
description: Crie funções de retorno de chamada após enviar uma ocorrência para a Adobe.
feature: Appmeasurement Implementation
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/Hk3K6cOITndpRE4xrWzEEu1n-JcV-U8A1lO8iUWssUY'
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
source-wordcount: 435
ht-degree: 54%

---

# registerPreTrackCallback

A variável `registerPreTrackCallback` permite que sua organização execute uma função JavaScript após um URL de solicitação de imagem ser compilado, mas antes de ser enviado. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement a um parceiro ou infraestrutura interna.

>[!WARNING]
>
>Não faça nenhuma chamada de rastreamento como [`t()`](t-method.md) ou [`tl()`](tl-method.md) dentro da variável `registerPreTrackCallback`. A definição de chamadas de rastreamento nessa variável causa um loop infinito de solicitações de imagem!

Cada vez que chama a variável `registerPreTrackCallback`, você faz com que essa função seja executada sempre que um URL de solicitação de imagem for compilado. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

>[!NOTE]
>
>O tempo e a ordem das funções disparadas entre `registerPreTrackCallback` e `registerPostTrackCallback` não são garantidos. Evite dependências entre essas duas funções.

## Pré-rastrear retorno de chamada usando a extensão Web SDK

O Web SDK não pode conectar uma função após a compilação de dados, mas antes do envio para o Adobe. No entanto, você pode usar `onBeforeEventSend` para registrar uma função para ser executada antes que os dados sejam enviados.

1. Faça logon na interface da [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleção de dados], clique no botão **[!UICONTROL Editar em antes de enviar o código de retorno de chamada]**.
1. Coloque o código desejado no editor.

## Pré-rastrear retorno de chamada implementando manualmente o Web SDK

O Web SDK não pode conectar uma função após a compilação de dados, mas antes do envio para o Adobe. No entanto, você pode usar `onBeforeEventSend` para registrar uma função para ser executada antes que os dados sejam enviados, semelhante a `doPlugins`. Consulte [Modificando eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do Web SDK para obter mais informações.

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
