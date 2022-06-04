---
title: trackOffline
description: Ative ou desative o rastreamento offline, o que altera a forma como o AppMeasurement coleta dados.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 100%

---

# trackOffline

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `trackOffline` determina se você deseja usar o rastreamento offline na implementação.

>[!WARNING]
>
>Você deve configurar seu conjunto de relatórios para aceitar ocorrências com carimbo de data e hora antes de habilitar essa variável. Se um conjunto de relatórios não aceitar ocorrências com carimbo de data e hora e essa variável estiver ativada, esses dados serão perdidos e não poderão ser recuperados.

Quando ativado, o AppMeasurement usa o seguinte processo para enviar dados para a Adobe:

* Ao compilar uma solicitação de imagem, um parâmetro de string de consulta de carimbo de data e hora é incluído.
* Se o dispositivo não conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência será armazenada localmente no dispositivo.
* Durante cada ocorrência subsequente, o AppMeasurement tenta enviar uma solicitação de imagem para a Adobe.
   * Se não conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência será adicionada à fila no dispositivo.
   * Se conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência e a fila de ocorrências de quando o dispositivo estava offline serão enviadas.

## Rastrear offline usando tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.trackOffline no AppMeasurement e no editor de código personalizado do

A variável `s.trackOffline` é do tipo booliano e ativa ou desativa o rastreamento offline. O valor padrão é `false`. Defina esse valor como `true` se desejar ativar o rastreamento offline.

```js
s.trackOffline = true;
```
