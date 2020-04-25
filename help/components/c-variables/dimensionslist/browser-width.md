---
description: Métricas que se referem à distância horizontal/vertical dos dados somente na janela do navegador. De maneira mais específica, o navegador
title: Largura/altura do navegador
topic: Metrics
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Largura/altura do navegador

Métricas que se referem à distância horizontal/vertical dos dados somente na janela do navegador. De maneira mais específica, o navegador

O Adobe Analytics utiliza somente a altura e a largura do navegador da primeira ocorrência de uma visita. O resto das ocorrências não recebem a atribuição da mesma visita.
As dimensões de largura/altura do navegador capturam valores similares mas distintos ao serem comparados com o [tamanho da tela móvel](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150).

Por exemplo, ao analisar a largura ou a altura do navegador em relação à resolução dos dispositivos móveis, será necessário estar ciente destas distinções:

* As Resoluções de dispositivos móveis são os valores físicos associados ao dispositivo. Por exemplo, em Resoluções de dispositivos móveis, o Galaxy S8 apareceria como 2.960 x 1.440. A resolução do dispositivo móvel é obtida por meio de um serviço terceirizado após a identificação do dispositivo.
* Por outro lado, nos valores de altura e largura do navegador, você verá os valores CSS (lógicos) de 740 x 360. Os valores do navegador dependem dos dados de Javascript/CSS.
* Para uma breve discussão, consulte [este tópico](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio).

