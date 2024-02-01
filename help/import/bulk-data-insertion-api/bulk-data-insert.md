---
title: API de inserção de dados em massa
description: A API de inserção de dados em massa (BDIA) é um recurso do Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos, em vez de usar bibliotecas do lado do cliente, como o AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 84%

---

# API de inserção de dados em massa

A inserção de dados em massa soluciona vários casos de uso, como:

* Inserção de dados históricos de um sistema de análises anterior

* Um sistema interno de coleta de análises que inviabiliza o uso do AppMeasurement. Você pode usar os processos Extract-Transform-Load (ETL) para colocar dados em arquivos em lote e usar a BDIA para carregá-los no Adobe Analytics.

* Coleta de dados de dispositivos que têm apenas conectividade intermitente com a Internet. Esses dispositivos armazenam as interações até que recebam uma conexão. O dispositivo pode então fazer upload dos dados de uma só vez, por meio da BDIA.

A API de inserção de dados e a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) são métodos usados para enviar dados de coleta do lado do servidor para o Adobe Analytics. As chamadas da API de inserção de dados aceitam um evento por vez. A API de inserção de dados em massa aceita arquivos formatados CSV contendo dados do evento, um evento por linha. Se você estiver trabalhando em uma nova implementação da coleção do lado do servidor, recomendamos usar a API de inserção de dados em massa.
