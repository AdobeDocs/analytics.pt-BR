---
title: Solução de problemas de prazos de entrega de solicitações do Data Warehouse
description: Determine possíveis problemas com uma solicitação do Data Warehouse que pode prolongar os prazos de entrega.
feature: Data Warehouse
exl-id: eed4d172-fffd-453f-ab5b-0fc2a79d5bd0
source-git-commit: d929e97a9d9623a8255f16729177d812d59cec05
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 59%

---

# Resolver problemas de prazos de entrega de solicitações do Data Warehouse

Uma determinada solicitação do Data Warehouse pode levar de menos de uma hora a vários dias ou mais. É difícil estimar a quantidade exata de tempo que uma solicitação leva para ser processada devido aos seguintes fatores:

* O intervalo de datas da solicitação
* A quantidade de tráfego que seu conjunto de relatórios recebeu durante o período solicitado
* O número de regras em um segmento e quais variáveis em um segmento usaram
* Quantos dados estão incluídos no segmento
* O número de detalhamentos usados e o número de valores únicos em cada detalhamento
* O número de métricas usadas
* O número de solicitações simultâneas que estão sendo processadas
* Regras VISTA, se configuradas para serem aplicadas a solicitações do Data Warehouse

## Alterar solicitações para acelerar a entrega

Se as solicitações do Data Warehouse forem consistentemente demoradas, considere alterar as solicitações. Alterar uma solicitação é a única maneira de acelerar o delivery de uma solicitação Data Warehouse.

Para acelerar o delivery de uma solicitação Data Warehouse, você pode alterá-la de qualquer uma das seguintes maneiras:

* **Usar um segmento que contenha uma amostra menor de dados**: Quanto menos dados uma solicitação precisar para funcionar, mais rápido ela retornará um relatório.
* **Executar solicitações em incrementos de 14 dias ou menos**: solicitações menores são processadas mais rapidamente do que solicitações grandes.
* **Usar menos detalhamentos:** muitos detalhamentos em uma solicitação aumentam exponencialmente o tempo necessário para processá-la.

## Usar um método alternativo

Se você precisar desses tipos de relatórios em tempo hábil, considere as seguintes alternativas:

* **Analysis Workspace**: embora os itens de dimensão ilimitados não estejam disponíveis, ele inclui quase todos os outros casos de uso que o Data Warehouse oferece.
* **Feed de dados**: pega todos os dados brutos em um conjunto de relatórios diariamente e os envia para um destino na nuvem. Em seguida, você pode importar os dados para seu próprio banco de dados e executar queries para obter os dados necessários.
* **Solução de serviços de engenharia personalizados**: os Serviços de engenharia da Adobe podem fornecer uma solução personalizada para sua organização a um custo adicional. Entre em contato com a equipe de conta do Adobe para obter mais detalhes.
