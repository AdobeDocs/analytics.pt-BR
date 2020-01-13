---
title: useBeacon
description: useBeacon permite forçar o AppMeasurement a usar a API sendBeacon dos navegadores
keywords: Analytics Implementation
translation-type: ht
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# s.useBeacon

A variável `s.useBeacon` força a próxima solicitação a usar a [API sendBeacon](https://developer.mozilla.org/pt-BR/docs/Web/API/Navigator/sendBeacon) do navegador. Usar `s.sendBeacon` permite que uma solicitação HTTP seja enviada fora do contexto de uma página. É útil para links de saída e outras situações nas quais você deseja enviar informações antes que a página seja descarregada.

A configuração desse valor se aplica somente à próxima solicitação que o AppMeasurement aciona. Depois que a solicitação é acionada, o `s.useBeacon` é redefinido como false. Essa variável se aplica às solicitações de imagem `s.t()` e `s.tl()` imagem.

O uso da variável `s.useBeacon` exige o AppMeasurement 2.17.0 ou superior.

> [!NOTE]Os [Links de saída](s-linktrackvars.md) usam essa variável automaticamente sem qualquer configuração adicional.

## Sintaxe

```js
s.useBeacon = true;
```
