---
title: API de inserção de dados em massa
description: A API de inserção de dados em massa (BDIA) é um recurso da Adobe Analytics que permite carregar dados de chamadas do servidor em lotes de arquivos, em vez de usar bibliotecas do lado do cliente, como o AppMeasurement. As chamadas de servidor nesses arquivos em lote podem ser dados atuais (ao vivo) ou dados históricos. É um sucessor mais escalável da API de inserção de dados em versões anteriores da API do Adobe Analytics.
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---


# API de inserção de dados em massa

A inserção de dados em massa resolve vários casos de uso, como:

* Inserção de dados históricos de um sistema de análise anterior

* Um sistema interno de coleta de análises que inviabiliza o uso do AppMeasurement. Você pode usar os processos Extract-Transform-Load (ETL) para colocar dados em arquivos em lote e usar o BDIA para carregá-los no Adobe Analytics.

* Coleta de dados de dispositivos que têm apenas conectividade intermitente com a Internet. Esses dispositivos armazenam as interações até que recebam uma conexão. O dispositivo pode fazer upload dos dados de uma só vez via BDIA.

API de inserção de dados e [API de inserção de dados em massa](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=pt-BR#!AdobeDocs/analytics-2.0-apis/master/bdia.md)ambos são métodos para enviar dados de coleta do lado do servidor para o Adobe Analytics. As chamadas da API de inserção de dados aceitam um evento por vez. A API de inserção de dados em massa aceita arquivos formatados CSV contendo dados do evento, um evento por linha. Se você estiver trabalhando em uma nova implementação da coleção do lado do servidor, recomendamos usar a API de inserção de dados em massa.