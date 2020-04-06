---
title: trackOffline
description: Ative ou desative o rastreamento offline, o que altera a forma como o AppMeasurement coleta dados.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# trackOffline

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

A variável `trackOffline` determina se você deseja usar o rastreamento offline na implementação.

>[!IMPORTANT] Você deve configurar seu conjunto de relatórios para aceitar ocorrências com carimbo de data e hora antes de habilitar essa variável. Se um conjunto de relatórios não aceitar ocorrências com carimbo de data e hora e essa variável estiver ativada, esses dados serão perdidos e não poderão ser recuperados.

Quando ativado, o AppMeasurement usa o seguinte processo para enviar dados para a Adobe:

* Ao compilar uma solicitação de imagem, um parâmetro de string de consulta de carimbo de data e hora é incluído.
* Se o dispositivo não conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência será armazenada localmente no dispositivo.
* Durante cada ocorrência subsequente, o AppMeasurement tenta enviar uma solicitação de imagem para a Adobe.
   * Se não conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência será adicionada à fila no dispositivo.
   * Se conseguir acessar os servidores de coleta de dados da Adobe, a ocorrência e a fila de ocorrências de quando o dispositivo estava offline serão enviadas.

## Rastrear offline no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.trackOffline no AppMeasurement e no editor de código personalizado do Launch

A variável `s.trackOffline` é do tipo booliano e ativa ou desativa o rastreamento offline. O valor padrão é `false`. Defina esse valor como `true` se desejar ativar o rastreamento offline.

```js
s.trackOffline = true;
```
