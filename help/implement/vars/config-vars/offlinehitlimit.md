---
title: offlineHitLimit
description: Determine o número máximo de ocorrências a serem colocadas em fila para rastreamento offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 88%

---

# offlineHitLimit

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `offlineHitLimit` coloca um limite no número de ocorrências que o dispositivo armazena localmente. Essa variável só funciona se o [`trackOffline`](trackoffline.md) estiver ativado.

## Limite de ocorrências offline usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineHitLimit no AppMeasurement e o editor de código personalizado da extensão do Analytics

A variável `s.offlineHitLimit` é um número inteiro que representa o número máximo de ocorrências que um dispositivo armazena enquanto está offline. Se essa variável não estiver definida, não há limite para o número de ocorrências que um dispositivo armazena quando está offline.

```js
s.offlineHitLimit = 100;
```
