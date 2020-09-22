---
description: Requisitos de sistema e comparação da Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
translation-type: ht
source-git-commit: 322e2e87ab532d5e8a864dc06613a9b275c71df5
workflow-type: ht
source-wordcount: '432'
ht-degree: 100%

---


# Analytics Comparação e requisitos de produtos do

Esta página contém uma comparação de vários produtos do Adobe Analytics: Analysis Workspace, Reports &amp; Analytics, Report Builder, Data Warehouse, Data Workbench, Feeds de dados e API 2.0 do Analytics.

Para obter informações sobre qual produto Adobe Analytics usar, acesse [aqui](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome do produto e link de ajuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Reports &amp; Analytics](/help/analyze/reports-analytics/getting-started.md) | [Report Builder](/help/analyze/report-builder/home.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Data Workbench](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/home.html) | [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) | [API 2.0 do Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|---|---|
| **Método de acesso** | [Navegador](/help/admin/sys-reqs.md) | [Navegador](/help/admin/sys-reqs.md) | [MS Excel para Windows](/help/analyze/report-builder/setup/system-requirements.md) | Configure pelo navegador. [Saiba mais](/help/admin/sys-reqs.md) | [Windows de 64 bits](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/install/c-data-workbench-client-install.html) | Configure pelo navegador. [Saiba mais](/help/export/analytics-data-feed/data-feed-overview.md) | Ferramentas RESTful API. Faça logon com as credenciais de E/S da Adobe. [Saiba mais](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
| **Granularidade de dados** | Agregado | Agregado | Agregado | Agregado | Ocorrência | Ocorrência | Agregado |
| **Experience Cloud ID (ECID) disponível** | Não | Não | Não | Sim | Sim | Sim | Não |
| **Carimbo de data e hora disponível** | Não | Não | Não | Não | Sim | Sim | Não |
| **Nível de processamento** | Totalmente processado | Totalmente processado, com [relatório em tempo real](/help/components/c-real-time-reporting/realtime.md) separado | Totalmente processado, com [relatório em tempo real](/help/components/c-real-time-reporting/realtime.md) separado | Totalmente processado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Inclusão dos dados do filtro de bot do administrador** <br> [Saiba mais](/help/admin/admin/bot-removal/bot-removal.md) | Não | Sim - relatório de bot separado | Sim - relatório de bot separado | Não | Não | Não | Não |
| **Baixo tráfego (únicos excedidos) aparece** <br> [Saiba mais](/help/technotes/low-traffic.md) | Sim | Sim | Sim | Não | Não | Não | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 200 | 50000 | Ilimitado | Ilimitado | Ilimitado | 50000 |
| **Vários conjuntos de relatórios** | [Sim](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sim, com limitações | Sim | Não | Sim | Não | Sim |
| **Quantidade de detalhamentos** | Ilimitado | Até 2 | Até 2 | Ilimitado | Ilimitado | Ilimitado | Ilimitado, executar em vários queries |
| **Segmentação** <br> [Saiba mais](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sim | Sim | Sim | Sim, com [limitações](/help/components/segmentation/seg-reference/seg-compatibility.md) | Sim | Não | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/c-calcmetrics/cm-overview.md) | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Sim | Sim | Não | Sim | Não | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canais de marketing** <br> [Saiba mais](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sim | Sim | Sim | Sim | Sim | Sim - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sim |
| **Análise de coorte** | [Sim](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Não | Não | Não | Sim | Não | Não |
| **Atribuição** | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Limitado | Não | Sim | Não | Sim, com [Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Recursos do analista virtual** <br> [Saiba mais](/help/analyze/analysis-workspace/virtual-analyst/overview.md) | Sim | Não | Não | Não | Não | Não | Sim |
| **Preparação** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/curate.md) | Sim - Projeto e VRS | Não | Não | Não | Não | Não | Sim - apenas VRS |
| **Compartilhamento de projeto** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sim, com funções de projeto | Sim | Sim | Não | Sim | Não | Não |
| **Delivery programado** | Sim | Sim | Sim | Sim | Não | Sim | Não |
| **Destinos do delivery** | Email | Email | Email, FTP, SFTP, [publicação no Microsoft Power BI](/help/analyze/report-builder/c-publish-power-bi/power-bi.md) | Email, FTP. Entre em contato com o Atendimento ao cliente para obter suporte de destino adicional, incluindo SFTP, Azure Blob, Amazon S3 | - | FTP, SFTP, Azure Blob, Amazon S3 | - |
| **Processamento de tempo do relatório VRS** <br> [Saiba mais](/help/components/vrs/vrs-report-time-processing.md) | Sim | Não | Não | Não | Não | Não | Sim |
