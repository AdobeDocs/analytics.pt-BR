---
title: offlineThrottleDelay
description: Estabelece a frequência de ocorrências quando um dispositivo volta a ficar online.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 83%

---

# offlineThrottleDelay

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

Quando um dispositivo volta a ficar online, todas as ocorrências armazenadas no dispositivo são enviadas para os servidores de coleta de dados da Adobe. Um grande número de ocorrências em fila pode afetar o desempenho em dispositivos mais antigos. Use a variável `offlineThrottleDelay` para determinar com que frequência as ocorrências em fila são enviadas para a Adobe.

## Atraso de limitação offline usando o Web SDK

O Web SDK não oferece suporte ao rastreamento offline.

## Atraso de limitação offline usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineThrottleDelay no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.offlineThrottleDelay` é um número inteiro que representa o número de milissegundos que o AppMeasurement aguarda entre o envio de ocorrências em fila. Seu valor padrão é `0`, o que significa que todas as ocorrências em fila são enviadas ao mesmo tempo. Se `trackOffline` for `false`, essa variável não fará nada.

```js
s.offlineThrottleDelay = 500;
```
