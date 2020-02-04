---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
translation-type: tm+mt
source-git-commit: 979a95ca749a3e21c4ddf48ba2d2a95672938a20

---


# useBeacon

A maioria dos navegadores modernos inclui o método nativo `navigator.sendBeacon()`. Ele envia de forma assíncrona uma pequena quantidade de dados por HTTP para um servidor da Web. O AppMeasurement pode usar o `navigator.sendBeacon()` método se a `useBeacon` variável estiver ativada. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

Se `useBeacon` estiver ativado, a próxima ocorrência enviada para a Adobe usará o `navigator.sendBeacon()` método do navegador em vez de uma solicitação de `GET` imagem padrão. Essa variável se aplica às solicitações de imagem `s.t()` e `s.tl()` imagem. Ela requer o AppMeasurement 2.17.0 ou superior.

> [!TIP] O AppMeasurement ativa automaticamente `useBeacon` para solicitações de imagem de link de saída.

A `useBeacon` variável é ignorada quando o visitante usa um navegador sem suporte `navigator.sendBeacon()`.

## Usar beacon no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.useBeacon no AppMeasurement e Iniciar editor de código personalizado

A `s.useBeacon` variável é um booleano que determina se o AppMeasurement usa o `navigator.sendBeacon()` método do navegador. Its default value is `false`. Defina essa variável como `true` antes de chamar uma função de rastreamento se desejar usar a natureza assíncrona de `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

> [!NOTE] Depois que uma chamada de rastreamento é executada, essa variável é redefinida como `false`. Se sua implementação enviar várias solicitações de imagem no mesmo carregamento de página (como aplicativos de página única), defina essa variável como `true` antes de cada chamada de rastreamento.
