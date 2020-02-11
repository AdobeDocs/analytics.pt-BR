---
title: registerPostTrackCallback
description: Crie funções de retorno de chamada após enviar uma ocorrência para a Adobe.
translation-type: tm+mt
source-git-commit: acfcb1f27650649581875680e7897e5c9813765a

---


# registerPostTrackCallback

A `registerPostTrackCallback` variável permite que sua organização conecte uma função JavaScript imediatamente depois que uma ocorrência é enviada com êxito para a Adobe. Se uma chamada de rastreamento falhar, essa função não será executada. Você pode usar essa variável para enviar dados coletados pelo AppMeasurement para um parceiro ou infraestrutura interna, ou limpar valores variáveis em aplicativos de página única.

> [!IMPORTANT] Não chame nenhuma função de rastreamento como `t` ou `tl` dentro da `registerPostTrackCallback` variável. As funções de rastreamento nesta variável causam um loop infinito de solicitações de imagem!

Cada vez que você chama a `registerPostTrackCallback` variável, conecta essa função para ser executada imediatamente depois que uma solicitação de imagem é enviada com êxito. Evite registrar a mesma função várias vezes no mesmo carregamento de página.

> [!NOTE] O tempo e a ordem das funções disparadas entre `registerPreTrackCallback` e não `registerPostTrackCallback` são garantidos. Evite dependências entre essas duas funções.

## Registrar retorno de chamada de rastreamento de postagem no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.registerPostTrackCallback no editor de código personalizado do AppMeasurement e Launch

A função `s.registerPostTrackCallback` é uma função que utiliza uma função como seu único argumento. A função aninhada é executada antes do envio de uma solicitação de imagem.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se você quiser usar o URL da solicitação de imagem em seu código, consulte o argumento da `requestUrl` string na função aninhada. Você pode analisar a `requestUrl` variável para o uso desejado; o ajuste dessa variável não afeta a coleta de dados.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Argumentos adicionais podem ser incluídos na `s.registerPostTrackCallback` função, que pode ser usada na função aninhada:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Exemplo de caso de uso

O registro da `clearVars()` função no retorno de chamada pós-rastreamento pode ser benéfico para aplicativos de página única. Toda vez que você envia uma ocorrência para a Adobe com êxito, a `clearVars()` função é executada. Sua implementação pode definir variáveis novamente sem se preocupar com valores que persistem incorretamente.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
