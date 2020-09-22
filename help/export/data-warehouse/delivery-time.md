---
title: Resolver problemas de prazos de entrega de solicitações do Data Warehouse
description: Determine possíveis problemas com uma solicitação do Data Warehouse que pode prolongar os prazos de entrega.
translation-type: ht
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: ht
source-wordcount: '330'
ht-degree: 100%

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

Se as solicitações do Data Warehouse forem consistentemente demoradas, considere alterar as solicitações para adaptar o seguinte:

* **Usar um segmento que contenha uma amostra menor de dados**: Quanto menos dados uma solicitação precisar para funcionar, mais rápido ela retornará um relatório.
* **Executar solicitações em incrementos de 14 dias ou menos**: solicitações menores são processadas mais rapidamente do que solicitações grandes.
* **Usar menos detalhamentos:** muitos detalhamentos em uma solicitação do Data Warehouse aumentam exponencialmente o tempo necessário para o processamento.

>[!IMPORTANT]
>
> *Não há como acelerar o delivery de uma solicitação do Data Warehouse.*

Se você precisar desses tipos de relatórios em tempo hábil, considere as seguintes alternativas:

* **Analysis Workspace**: embora os itens de dimensão ilimitados não estejam disponíveis, ele inclui quase todos os outros casos de uso que o Data Warehouse oferece.
* **Feed de dados**: pega todos os dados brutos em um conjunto de relatórios diariamente e os envia para um site FTP. Em seguida, você pode importar esses dados para seu próprio banco de dados e executar queries para obter os dados que está procurando.
* **Solução de serviços de engenharia personalizados**: os Serviços de engenharia da Adobe podem fornecer uma solução personalizada para sua organização a um custo adicional. Entre em contato com o Gerente de conta da sua organização para obter mais detalhes.
