---
title: offlineThrottleDelay
description: Estabelece a frequência de ocorrências quando um dispositivo volta a ficar online.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: https://experienceleague.adobe.com/COxmVvMrt0ucZhReX3nYg1Ghacb-LBGcOsX50yzVQrY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 195
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
