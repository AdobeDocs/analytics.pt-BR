---
description: Requisitos de sistema e comparação da Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
translation-type: tm+mt
source-git-commit: 0885a42ccf79565d2ad55cf84e346926f2328f77
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 54%

---


# Analytics Comparação e requisitos de produtos do 

Esta página contém uma comparação de vários produtos Adobe Analytics: Analysis Workspace, Relatórios e Analytics, Report Builder, Data warehouse, Data Workbench, Feeds de dados e Analytics API 2.0.

Para obter informações sobre qual produto Adobe Analytics usar, acesse [aqui](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome do produto e link de ajuda | [Analysis Workspace](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/reports-analytics/getting-started.html) | [Report Builder](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/pt-BR/analytics/export/data-warehouse/data-warehouse.html) | [Data Workbench](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/home.html) | [Feeds de dados](https://docs.adobe.com/content/help/pt-BR/analytics/export/analytics-data-feed/data-feed-overview.html) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Método de acesso** | [Navegador](https://docs.adobe.com/content/help/pt-BR/analytics/admin/sys-reqs.html) | [Navegador](https://docs.adobe.com/content/help/pt-BR/analytics/admin/sys-reqs.html) | [MS Excel para Windows](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Configuração por meio do navegador. Os destinos suportados incluem FTP. Entre em contato com o Atendimento ao cliente para obter suporte adicional ao destino. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/admin/sys-reqs.html) | [Windows de 64 bits](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/install/c-data-workbench-client-install.html) | Configure pelo navegador. Os destinos suportados incluem FTP, SFTP, Blob do Azure, S3. [Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/export/analytics-data-feed/data-feed-overview.html) | Ferramentas RESTful API. Faça logon com as credenciais de E/S do Adobe. [Saiba mais](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Formato de dados (granularidade)** | Agregado | Agregado | Agregado | ECID | Carimbo de data e hora + ECID | Carimbo de data e hora + ECID | Agregado |
| **Nível de processamento** | Totalmente processado | Totalmente processado, com relatório separado em tempo [real](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Totalmente processado, com relatório separado em tempo [real](https://docs.adobe.com/content/help/en/analytics/components/real-time-reporting/realtime.html) | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Dados de filtro de robô de administrador incluídos** <br>[Saiba mais](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/bot-removal/bot-removal.html) | Não | Sim - relatório bot separado | Sim - relatório bot separado | Não | Não | Não | Não |
| **Baixo tráfego (Únicos excedidos) é exibido** <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/technotes/low-traffic.html) | Sim | Sim | Sim | Não | Não | Não | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 200 | 50000 | Ilimitado | Ilimitado | Ilimitado | 50000 |
| **Vários conjuntos de relatórios** | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.html) | Sim, com limitações | Sim | Não | Sim | Não | Sim |
| **Quantidade de interrupções** | Ilimitado | Até 2 | Até 2 | Ilimitado | Ilimitado | Ilimitado | Ilimitado, executar em vários query |
| **Segmentação** <br>[Saiba mais](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-workflow.html) | Sim | Sim | Sim | Sim, com [limitações](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segment-reference/seg-compatibility.html) | Sim | Não | Sim |
| **Métricas** calculadas <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/cm-overview.html) | Sim, com [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Sim | Sim | Não | Sim | Não | Sim, com [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Canais** de marketing <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/components/marketing-channels/c-getting-started-mchannel.html) | Sim | Sim | Sim | Sim | Sim | Sim - [va_finder, va_closer](https://docs.adobe.com/content/help/en/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html) | Sim |
| **análise de coorte** | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Não | Não | Não | Sim | Não | Não |
| **Atribuição** | Sim, com [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) | Limitado | Limitado | Não | Sim | Não | Sim, com [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution/overview.html) |
| **Analista virtual recursos** <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/virtual-analyst/overview.html) | Sim | Não | Não | Não | Não | Não | Sim |
| **Curation** <br>[Learn more](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html) | Sim - Projeto e VRS | Não | Não | Não | Não | Não | Sim - apenas VRS |
| **Compartilhamento** de projetos <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/share-projects.html) | Sim, com funções de projeto | Sim | Sim | Não | Sim | Não | Não |
| **Agendado o delivery** | Sim | Sim | Sim | Sim | Sim | Sim | Não |
| **Processamento** de tempo do relatório VRS <br>[Saiba mais](https://docs.adobe.com/content/help/pt-BR/analytics/components/virtual-report-suites/vrs-report-time-processing.html) | Sim | Não | Não | Não | Não | Não | Sim |
