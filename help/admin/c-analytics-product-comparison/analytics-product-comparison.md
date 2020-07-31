---
description: Requisitos de sistema e comparação da Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
translation-type: tm+mt
source-git-commit: 63a827b4cfa858e503431579755f1b4dba4b5bdf
workflow-type: tm+mt
source-wordcount: '432'
ht-degree: 54%

---


# Analytics Comparação e requisitos de produtos do

Esta página contém uma comparação de vários produtos Adobe Analytics: Analysis Workspace, Relatórios e Analytics, Report Builder, Data warehouse, Data Workbench, Feeds de dados e Analytics API 2.0.

Para obter informações sobre qual produto Adobe Analytics usar, acesse [aqui](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome do produto e link de ajuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/home.html) | [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) | [Analytics API 2.0](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| **Método de acesso** | [Navegador](/help/admin/sys-reqs.md) | [Navegador](/help/admin/sys-reqs.md) | [MS Excel para Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configure pelo navegador. [Saiba mais](/help/admin/sys-reqs.md) | [Windows de 64 bits](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/install/c-data-workbench-client-install.html) | Configure pelo navegador. [Saiba mais](/help/export/analytics-data-feed/data-feed-overview.md) | Ferramentas RESTful API. Faça logon com as credenciais de E/S do Adobe. [Saiba mais](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularidade de dados** | Agregado | Agregado | Agregado | Agregado | Ocorrência | Ocorrência | Agregado |
| **Experience Cloud ID (ECID) disponível** | Não | Não | Não | Sim | Sim | Sim | Não |
| **Carimbo de data e hora disponível** | Não | Não | Não | Não | Sim | Sim | Não |
| **Nível de processamento** | Totalmente processado | Totalmente processado, com relatório separado em tempo [real](/help/components/c-real-time-reporting/realtime.md) | Totalmente processado, com relatório separado em tempo [real](/help/components/c-real-time-reporting/realtime.md) | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Inclusão dos dados do filtro do robô de administração** <br> [Saiba mais](/help/admin/admin/bot-removal/bot-removal.md) | Não | Sim - relatório bot separado | Sim - relatório bot separado | Não | Não | Não | Não |
| **Baixo tráfego (Únicos excedidos) é exibido** <br> [Saiba mais](/help/technotes/low-traffic.md) | Sim | Sim | Sim | Não | Não | Não | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 200 | 50000 | Ilimitado | Ilimitado | Ilimitado | 50000 |
| **Vários conjuntos de relatórios** | [Sim](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sim, com limitações | Sim | Não | Sim | Não | Sim |
| **Quantidade de interrupções** | Ilimitado | Até 2 | Até 2 | Ilimitado | Ilimitado | Ilimitado | Ilimitado, executar em vários query |
| **Segmentação** <br> [Saiba mais](/help/components/c-segmentation/c-segmentation-workflow/seg-workflow.md) | Sim | Sim | Sim | Sim, com [limitações](/help/components/c-segmentation/seg-reference/seg-compatibility.md) | Sim | Não | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/c-calcmetrics/cm-overview.md) | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Sim | Sim | Não | Sim | Não | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canais de marketing** <br> [Saiba mais](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sim | Sim | Sim | Sim | Sim | Sim - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sim |
| **análise de coorte** | [Sim](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Não | Não | Não | Sim | Não | Não |
| **Atribuição** | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Limitado | Não | Sim | Não | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Recursos do analista virtual** <br> [Saiba mais](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Sim | Não | Não | Não | Não | Não | Sim |
| **Preparação** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/curate.md) | Sim - Projeto e VRS | Não | Não | Não | Não | Não | Sim - apenas VRS |
| **Compartilhamento de projetos** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sim, com funções de projeto | Sim | Sim | Não | Sim | Não | Não |
| **Agendado o delivery** | Sim | Sim | Sim | Sim | Não | Sim | Não |
| **Destinos do Delivery** | Email | Email | Email, FTP, SFTP, [publicação no Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Email, FTP. Entre em contato com o Atendimento ao cliente para obter suporte de destino adicional, incluindo SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Blob do Azure, Amazon S3 | - |
| **Processamento de tempo do relatório VRS** <br> [Saiba mais](/help/components/vrs/vrs-report-time-processing.md) | Sim | Não | Não | Não | Não | Não | Sim |
