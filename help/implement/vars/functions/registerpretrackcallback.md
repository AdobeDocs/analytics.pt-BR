---
title: registerPreTrackCallback
description: Crie funções de retorno de chamada após enviar uma ocorrência para a Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 100%

---

# registerPreTrackCallback

A variável `registerPreTrackCallback` permite que sua organização execute uma função JavaScript após um URL de solicitação de imagem ser compilado, mas antes de ser enviado. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement a um parceiro ou infraestrutura interna.

>[!IMPORTANT]
>
>Não chame nenhuma função de rastreamento como [`t()`](t-method.md) ou [`tl()`](tl-method.md) dentro da variável [`registerPostTrackCallback`](registerposttrackcallback.md). As funções de rastreamento nesta variável causam um loop infinito de solicitações de imagem!

Cada vez que chama a variável `registerPreTrackCallback`, você faz com que essa função seja executada sempre que um URL de solicitação de imagem for compilado. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

>[!NOTE]
>
>O tempo e a ordem das funções disparadas entre `registerPreTrackCallback` e `registerPostTrackCallback` não são garantidos. Evite dependências entre essas duas funções.

## Registrar retorno de chamada pré-rastreamento na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.registerPreTrackCallback no AppMeasurement e no editor de código personalizado do 

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
