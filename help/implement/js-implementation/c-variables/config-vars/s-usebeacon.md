---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
keywords: Analytics Implementation
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

A `s.useBeacon` variável força a próxima solicitação a usar a API [](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon)sendBeacon do navegador. Usar `s.sendBeacon` permite que uma solicitação HTTP seja enviada fora do contexto de uma página. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

A configuração desse valor se aplica somente à próxima solicitação que o AppMeasurement aciona. Depois que a solicitação é acionada, `s.useBeacon` redefine para false. Essa variável se aplica às solicitações de imagem `s.t()` e `s.tl()` imagem.

O uso da `s.useBeacon` variável exige o AppMeasurement 2.17.0 ou superior.

> [!NOTE] Links [de](s-linktrackvars.md) saída usam essa variável automaticamente sem qualquer configuração adicional.

## Sintaxe

```js
s.useBeacon = true;
```
