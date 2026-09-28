---
title: trackOffline
description: Habilite ou desabilite o rastreamento offline, o que altera a forma como o AppMeasurement coleta dados.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/6VDAO0-QMXqia2Ddy1uPcxnTrlJi49B8zjaLcC0HawU'
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
source-wordcount: '283'
ht-degree: 89%
---
# trackOffline

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, os hits são armazenados em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `trackOffline` determina se você deseja usar o rastreamento offline na implementação.

>[!WARNING]
>
>Você deve configurar seu conjunto de relatórios para aceitar hits com carimbo de data e hora antes de habilitar essa variável. Se um conjunto de relatórios não aceitar hits com carimbo de data e hora e essa variável estiver habilitada, esses dados serão perdidos e não poderão ser recuperados.

Quando habilitado, o AppMeasurement usa o seguinte processo para enviar dados para a Adobe:

* Ao compilar uma solicitação de imagem, um parâmetro de string de consulta de carimbo de data e hora é incluído.
* Se o dispositivo não conseguir acessar os servidores de coleta de dados da Adobe, o hit será armazenado localmente no dispositivo.
* Durante cada hit subsequente, o AppMeasurement tenta enviar uma solicitação de imagem para a Adobe.
  * Se não conseguir acessar os servidores de coleta de dados da Adobe, o hit será adicionado à fila no dispositivo.
  * Se conseguir acessar os servidores de coleta de dados da Adobe, o hit e a fila de hits de quando o dispositivo estava offline serão enviados.

## Rastreamento offline usando o Web SDK

O Web SDK não oferece suporte ao rastreamento offline.

## Rastreamento offline usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.trackOffline no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.trackOffline` é do tipo booliano e habilita ou desabilita o rastreamento offline. O valor padrão é `false`. Defina esse valor como `true` se desejar habilitar o rastreamento offline.

```js
s.trackOffline = true;
```
