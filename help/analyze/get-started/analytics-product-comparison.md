---
description: Requisitos de sistema e comparação do Analysis Workspace, Reports Builder, Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
source-git-commit: 9a2d4c582b6a3946b658924851e5b5ada2f5a7ee
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 100%

---

# Comparação e requisitos de produtos do Analytics

Esta página contém uma comparação de vários produtos do Adobe Analytics: Analysis Workspace, Report Builder, Data Warehouse, Data Feeds e API 2.0 do Analytics.

Para obter informações sobre qual produto do Adobe Analytics usar, consulte [Qual ferramenta do Adobe Analytics devo usar?](/help/analyze/get-started/which-analytics-tool.md).

| Nome do produto e link de ajuda | [Analysis Workspace](/help/analyze/analysis-workspace/home.md) | [Report Builder](/help/analyze/report-builder/rb-overview.md) | [Data Warehouse](/help/export/data-warehouse/data-warehouse.md) | [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md) | [API 2.0 do Analytics](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) |
|---|---|---|---|---|---|
| **Método de acesso** | [Navegador](/help/analyze/get-started/sys-reqs.md) | [MS Excel para Windows](/help/analyze/legacy-report-builder/setup/system-requirements.md) | Configure pelo navegador. [Saiba mais](/help/analyze/get-started/sys-reqs.md) | Configure pelo navegador. [Saiba mais](/help/export/analytics-data-feed/data-feed-overview.md) | Ferramentas RESTful API. Faça logon com as credenciais do Adobe Developer. [Saiba mais](https://developer.adobe.com/analytics-apis/docs/2.0/) |
| **Granularidade de dados** | Agregado | Agregado | Agregado | Ocorrência | Agregado |
| **Experience Cloud ID (ECID) disponível** | Não | Não | Sim | Sim | Não |
| **Carimbo de data e hora disponível** | Não | Não | Não | Sim | Não |
| **Nível de processamento** | Totalmente processado | Totalmente processado, com [relatório em tempo real](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime.md) separado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Inclusão dos dados do filtro de bot do administrador** <br> [Saiba mais](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-removal.md) | Não | Sim - relatório de bot separado | Não | Não | Não |
| **Baixo tráfego (únicos excedidos) aparece** <br> [Saiba mais](/help/technotes/low-traffic.md) | Sim | Sim | Não | Não | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 50000 | Ilimitado | Ilimitado | 50000 |
| **Vários conjuntos de relatórios** | [Sim](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sim | Não | Sim | Não | Sim |
| **Quantidade de detalhamentos** | Ilimitado | Até 2 | Ilimitado | Ilimitado | Ilimitado, executar em vários queries |
| **Segmentação** <br> [Saiba mais](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sim | Sim | Sim, com [limitações](/help/components/segmentation/seg-reference/seg-compatibility.md) | Não | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/c-calcmetrics/cm-overview.md) | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Sim, com Atribuição | Sim | Não | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canais de marketing** <br> [Saiba mais](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sim | Sim | Sim | Sim - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sim |
| **Análise de coorte** | [Sim](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sim | Não | Não | Não |
| **Atribuição** | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Não | Não | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Não |
| **Preparação** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/curate.md) | Sim: conjunto de relatórios de projeto e virtuais | Não | Não | Não | Sim: somente conjunto de relatórios virtuais |
| **Compartilhamento de projeto** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sim, com funções de projeto | Sim | Não | Não | Não |
| **Delivery programado** | Sim | Sim | Sim | Sim | Não |
| **Destinos do delivery** | Email | Email, FTP, SFTP, [publicação no Microsoft Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC e Email | Amazon S3, Azure RBAC, Azure SAS e Google Cloud Platform | - |
| **Processamento de tempo de relatório do conjunto de relatórios virtuais** <br> [Saiba mais](/help/components/vrs/vrs-report-time-processing.md) | Sim | Não | Não | Não | Sim |
