---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '158'
ht-degree: 100%

---

# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `offlineHitLimit` coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se o [`trackOffline`](trackoffline.md) estiver ativado.

## Limite de ocorrências offline usando tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e editor de código personalizado do 

A variável `s.offlineHitLimit` é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto está offline. Se essa variável não estiver definida, não há limite para o número de ocorrências que um dispositivo armazena quando está offline.

```js
s.offlineHitLimit = 100;
```
