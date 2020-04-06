---
title: registerPostTrackCallback
description: Cria funções de retorno de chamada após enviar uma ocorrência para a Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# registerPostTrackCallback

A variável `registerPostTrackCallback` permite que sua organização conecte uma função JavaScript imediatamente após uma ocorrência ser enviada com êxito para a Adobe. Se uma chamada de rastreamento falhar, essa função não será executada. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement a um parceiro ou infraestrutura interna, ou para limpar valores variáveis em aplicativos de página única.

>[!IMPORTANT] Não chame nenhuma chamada de rastreamento como [`t()`](t-method.md) ou [`tl()`](tl-method.md) dentro da `registerPostTrackCallback` variável. As funções de rastreamento nesta variável causam um loop infinito de solicitações de imagem!

Cada vez que chama a variável `registerPostTrackCallback`, você faz com que essa função seja executada imediatamente após uma solicitação de imagem ser enviada com êxito. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

>[!NOTE] O tempo e a ordem das funções disparadas entre [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` não são garantidos. Evite dependências entre essas duas funções.

## Registrar retorno de chamada pós-rastreamento no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.registerPostTrackCallback no AppMeasurement e no editor de código personalizado do Launch

`s.registerPostTrackCallback` é uma função que utiliza uma função como seu único argumento. A função aninhada é executada antes do envio de uma solicitação de imagem.

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

## Exemplo de caso de uso

O registro da função [`clearVars()`](clearvars.md) no retorno de chamada pós-rastreamento pode ser benéfico para aplicativos de página única. Toda vez que você envia uma ocorrência para a Adobe com êxito, a função `clearVars()` é executada. Sua implementação pode definir variáveis novamente sem se preocupar com valores que persistem incorretamente.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
