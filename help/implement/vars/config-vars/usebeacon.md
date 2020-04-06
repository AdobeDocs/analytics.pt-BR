---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# useBeacon

A maioria dos navegadores modernos inclui o método nativo `navigator.sendBeacon()`. Ele envia de forma assíncrona uma pequena quantidade de dados por HTTP para um servidor web. O AppMeasurement pode usar o método `navigator.sendBeacon()` se a variável `useBeacon` estiver ativada. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

Se `useBeacon` estiver ativado, a próxima ocorrência enviada para a Adobe usará o método `navigator.sendBeacon()` do navegador em vez de uma solicitação de imagem `GET` padrão. Essa variável se aplica às solicitações de imagem [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md). Ela requer o AppMeasurement versão 2.17.0 ou superior.

>[!TIP] O AppMeasurement ativa `useBeacon` automaticamente para solicitações de imagem de link de saída.

A variável `useBeacon` é ignorada quando o visitante usa um navegador sem suporte a `navigator.sendBeacon()`. O uso dessa variável exige o AppMeasurement 2.16.0 ou superior.

## Usar beacon no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.useBeacon no AppMeasurement e no editor de código personalizado do Launch

A variável `s.useBeacon` é do tipo booleano e determina se o AppMeasurement usa o método `navigator.sendBeacon()` do navegador. O valor padrão é `false`. Defina essa variável como `true` antes de chamar uma função de rastreamento se desejar usar a natureza assíncrona do `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE] Depois que uma chamada de rastreamento é executada, essa variável é redefinida como `false`. Se sua implementação enviar várias solicitações de imagem no mesmo carregamento de página (como no caso de aplicativos de página única), defina essa variável como `true` antes de cada chamada de rastreamento.
