---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `offlineHitLimit` coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se o [`trackOffline`](trackoffline.md) estiver ativado.

## Limite de ocorrências offline no Adobe Experience Platform Launch.

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e editor de código personalizado do Launch

A variável `s.offlineHitLimit` é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto está offline. Se essa variável não estiver definida, não há limite para o número de ocorrências que um dispositivo armazena quando está offline.

```js
s.offlineHitLimit = 100;
```
