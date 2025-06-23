---
title: registerPostTrackCallback
description: Cria funções de retorno de chamada após enviar uma ocorrência para a Adobe.
feature: Appmeasurement Implementation
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 73%

---

# registerPostTrackCallback

A variável `registerPostTrackCallback` permite que sua organização conecte uma função JavaScript imediatamente após uma ocorrência ser enviada com êxito para a Adobe. Se uma chamada de rastreamento falhar, essa função não será executada. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement a um parceiro ou infraestrutura interna, ou para limpar valores variáveis em aplicativos de página única.

>[!WARNING]
>
>Não faça nenhuma chamada de rastreamento como [`t()`](t-method.md) ou [`tl()`](tl-method.md) dentro da variável `registerPostTrackCallback`. A definição de chamadas de rastreamento nessa variável causa um loop infinito de solicitações de imagem!

Cada vez que chama a variável `registerPostTrackCallback`, você faz com que essa função seja executada imediatamente após uma solicitação de imagem ser enviada com êxito. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

>[!NOTE]
>
>O tempo e a ordem das funções disparadas entre [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` não são garantidos. Evite dependências entre essas duas funções.

## Retorno de chamada pós-rastreamento usando a extensão do Web SDK

Em breve!

## Retorno de chamada pós-rastreamento implementando manualmente o Web SDK

Você pode usar uma Promessa da JavaScript ao enviar um evento para registrar uma função depois que os dados forem enviados com êxito para a Adobe.

```js
alloy("sendEvent",{
  "xdm": {}
}).then(function(result) {
  Console.Log("Data was successfully sent.");
});
```

Consulte [Manipulando respostas de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#handling-responses-from-events) na documentação do Web SDK para obter mais informações.

## Registrar retorno de chamada pós-rastreamento usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.registerPostTrackCallback no AppMeasurement e no editor de código personalizado da extensão do Analytics

`s.registerPostTrackCallback` é uma função que utiliza uma função como seu único argumento. A função aninhada é executada imediatamente após o envio bem-sucedido de uma solicitação de imagem.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se você quiser usar o URL da solicitação de imagem em seu código, consulte o argumento em string de `requestUrl` na função aninhada. Você pode analisar a variável `requestUrl` para usá-la como desejar; o ajuste dessa variável não afeta a coleta de dados.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Argumentos adicionais podem ser incluídos na função `s.registerPostTrackCallback`, que pode ser usada na função aninhada:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Caso de uso

O registro da função [`clearVars()`](clearvars.md) no retorno de chamada pós-rastreamento pode ser benéfico para aplicativos de página única. Toda vez que você envia uma ocorrência para a Adobe com êxito, a função `clearVars()` é executada. Sua implementação pode definir variáveis novamente sem se preocupar com valores que persistem incorretamente.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
