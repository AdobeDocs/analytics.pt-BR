---
title: API de inserção de dados em massa
description: A API de inserção de dados em massa (BDIA) é um recurso do Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos, em vez de usar bibliotecas do lado do cliente, como o AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: 'https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 85%

---

# API de inserção de dados em massa

A inserção de dados em massa soluciona vários casos de uso, como:

* Inserção de dados históricos de um sistema de análises anterior

* Um sistema interno de coleta de análises que inviabiliza o uso do AppMeasurement. Você pode usar os processos Extract-Transform-Load (ETL) para colocar dados em arquivos em lote e usar a BDIA para carregá-los no Adobe Analytics.

* Coleta de dados de dispositivos que têm apenas conectividade intermitente com a Internet. Esses dispositivos armazenam as interações até que recebam uma conexão. O dispositivo pode então fazer upload dos dados de uma só vez, por meio da BDIA.

A API de inserção de dados e a [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md) são métodos usados para enviar dados de coleta do lado do servidor para o Adobe Analytics. As chamadas da API de inserção de dados aceitam um evento por vez. A API de inserção de dados em massa aceita arquivos formatados CSV contendo dados do evento, um evento por linha. Se você estiver trabalhando em uma nova implementação da coleção do lado do servidor, recomendamos usar a API de inserção de dados em massa.
