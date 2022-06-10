---
title: offlineThrottleDelay
description: Estabelece a frequência de ocorrências quando um dispositivo volta a ficar online.
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 81%

---

# offlineThrottleDelay

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

Quando um dispositivo volta a ficar online, todas as ocorrências armazenadas no dispositivo são enviadas para os servidores de coleta de dados da Adobe. Um grande número de ocorrências em fila pode afetar o desempenho em dispositivos mais antigos. Use a variável `offlineThrottleDelay` para determinar com que frequência as ocorrências em fila são enviadas para a Adobe.

## Atraso de aceleração offline usando a extensão Adobe Analytics

Não há um campo dedicado na extensão Adobe Analytics para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineThrottleDelay no AppMeasurement e no editor de código personalizado de extensão do Analytics

A variável `s.offlineThrottleDelay` é um número inteiro que representa o número de milissegundos que o AppMeasurement aguarda entre o envio de ocorrências em fila. Seu valor padrão é `0`, o que significa que todas as ocorrências em fila são enviadas ao mesmo tempo. Se `trackOffline` for `false`, essa variável não fará nada.

```js
s.offlineThrottleDelay = 500;
```
