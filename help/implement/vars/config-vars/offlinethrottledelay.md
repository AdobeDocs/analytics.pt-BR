---
title: offlineThrottleDelay
description: Estabelece a frequência de ocorrências quando um dispositivo retorna online.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

O rastreamento offline é uma maneira opcional de coletar dados no Adobe Analytics. Se um visitante se desconecta da Internet, mas continua a navegar em seu site, as ocorrências são armazenadas em uma fila offline até que o dispositivo se conecte novamente à Internet. O rastreamento offline é usado principalmente para aplicativos móveis.

Quando um dispositivo volta a ficar on-line, todas as ocorrências armazenadas no dispositivo são enviadas para os servidores de coleta de dados da Adobe. Um grande número de ocorrências em fila pode potencialmente afetar o desempenho em dispositivos mais antigos. Use a `offlineThrottleDelay` variável para determinar com que frequência as ocorrências em fila são enviadas para a Adobe.

## Atraso de aceleração offline no lançamento da plataforma Adobe Experience

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.offlineThrottleDelay no AppMeasurement e Iniciar editor de código personalizado

A `s.offlineThrottleDelay` variável é um número inteiro que representa o número de milissegundos que o AppMeasurement aguarda entre o envio de ocorrências em fila. Seu valor padrão é `0`, o que significa que todas as ocorrências em fila são enviadas ao mesmo tempo. Se `trackOffline` for `false`, essa variável não fará nada.

```js
s.offlineThrottleDelay = 500;
```
