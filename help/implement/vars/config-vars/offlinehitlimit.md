---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A `offlineHitLimit` variável coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se [`trackOffline`](trackoffline.md) estiver ativada.

## Limite de ocorrência offline no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e Iniciar editor de código personalizado

A `s.offlineHitLimit` variável é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto estão offline. Se essa variável não estiver definida, não há limite para o número de ocorrências que um dispositivo armazena quando está offline.

```js
s.offlineHitLimit = 100;
```
