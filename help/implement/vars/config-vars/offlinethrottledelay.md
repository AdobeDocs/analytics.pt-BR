---
title: offlineThrottleDelay
description: Estabelece a frequência de hits quando um dispositivo volta a ficar online.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 83%
---
# offlineThrottleDelay

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, os hits são armazenados em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

Quando um dispositivo volta a ficar online, todos os hits armazenados no dispositivo são enviados para os servidores de coleta de dados da Adobe. Um grande número de hits em fila pode afetar o desempenho em dispositivos mais antigos. Use a variável `offlineThrottleDelay` para determinar com que frequência os hits em fila são enviados para a Adobe.

## Atraso de limitação offline usando o Web SDK

O Web SDK não oferece suporte ao rastreamento offline.

## Atraso de limitação offline usando a extensão Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.offlineThrottleDelay no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.offlineThrottleDelay` é um número inteiro que representa o número de milissegundos que o AppMeasurement aguarda entre o envio de hits em fila. Seu valor padrão é `0`, o que significa que todos os hits em fila são enviados ao mesmo tempo. Se `trackOffline` for `false`, essa variável não fará nada.

```js
s.offlineThrottleDelay = 500;
```
