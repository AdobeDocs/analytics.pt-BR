---
title: registerPreTrackCallback
description: Crie funções de retorno de chamada antes de enviar uma ocorrência para a Adobe.
translation-type: tm+mt
source-git-commit: d1db8da65faac1bf09fa2a290a2645092b542a35

---


# registerPreTrackCallback

A `registerPreTrackCallback` variável permite que sua organização conecte uma função JavaScript depois que um URL de solicitação de imagem é compilado, mas antes de ser enviado. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement para um parceiro ou infraestrutura interna.

> [!IMPORTANT] Não chame nenhuma função de rastreamento como `t` ou `tl` dentro da `registerPostTrackCallback` variável. As funções de rastreamento nesta variável causam um loop infinito de solicitações de imagem!

Cada vez que você chama a `registerPreTrackCallback` variável, conecta essa função para ser executada sempre que um URL de solicitação de imagem for compilado. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

> [!NOTE] O tempo e a ordem das funções disparadas entre `registerPreTrackCallback` e não `registerPostTrackCallback` são garantidos. Evite dependências entre essas duas funções.

## Registrar retorno de chamada pré-rastreamento no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.registerPreTrackCallback no editor de código personalizado do AppMeasurement e Launch

A função `s.registerPreTrackCallback` é uma função que utiliza uma função como seu único argumento. A função aninhada é executada antes do envio de uma solicitação de imagem.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se você quiser usar o URL da solicitação de imagem em seu código, consulte o argumento da `requestUrl` string na função aninhada. Você pode analisar a `requestUrl` variável para o uso desejado; o ajuste dessa variável não afeta a coleta de dados.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Argumentos adicionais podem ser incluídos na `s.registerPreTrackCallback` função, que pode ser usada na função aninhada:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

> [!NOTE] Definir variáveis de página ou alterar a `requestUrl` string dentro dessa função *não* afeta a solicitação de imagem enviada logo após essa chamada de função.
