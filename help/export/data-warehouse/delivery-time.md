---
title: Solucionar problemas de tempos de delivery de solicitação de Data warehouse
description: Determine possíveis problemas com uma solicitação de Data warehouse que pode prolongar os tempos do delivery.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---


# Solucionar problemas de tempos de delivery de solicitação de Data warehouse

Uma determinada solicitação de Data warehouse pode levar de menos de uma hora a vários dias ou mais. É difícil estimar a quantidade exata de tempo que uma solicitação leva para ser processada, devido aos seguintes fatores:

* O intervalo de datas da solicitação
* A quantidade de tráfego que seu conjunto de relatórios recebeu durante o período solicitado
* O número de regras em um segmento e quais variáveis em um segmento usaram
* Quantos dados estão incluídos no segmento
* O número de detalhamentos usados e o número de valores únicos em cada detalhamento
* O número de métricas usadas
* O número de solicitações simultâneas que estão sendo processadas
* Regras VISTA, se configuradas para se aplicar a solicitações de DataWarehouse

Se você vir solicitações de data warehouse consistentemente demorando muito tempo, considere alterar suas solicitações para acomodar o seguinte:

* **Use um segmento que contenha uma amostra menor de dados**: Quanto menos dados uma solicitação funcionar, mais rápido ela retornará um relatório.
* **Execute solicitações em incrementos de 14 dias ou menos**: Solicitações menores são processadas mais rapidamente do que solicitações grandes.
* **Usar menos detalhamentos:** Muitos detalhamentos em uma solicitação de Data warehouse aumentam exponencialmente o tempo necessário para o processamento.

>[!IMPORTANT]
>
> *Não há como acelerar o delivery de uma solicitação de Data warehouse.*

Se você precisar desses tipos de relatórios de forma mais oportuna, considere as seguintes alternativas:

* **Analysis Workspace**: Embora itens de dimensão ilimitados não estejam disponíveis, inclui quase todos os outros casos de uso fornecidos pela Data warehouse.
* **Feed** de dados: Pega todos os dados brutos em um conjunto de relatórios diariamente e os envia para um site FTP. Em seguida, você pode importar esses dados para seu próprio banco de dados e executar query para obter os dados que está procurando.
* **Solução** de serviços de engenharia personalizados: Os Serviços de engenharia de Adobe podem fornecer uma solução personalizada para sua organização a um custo adicional. Entre em contato com o Gerente de conta de sua organização para obter mais detalhes.
