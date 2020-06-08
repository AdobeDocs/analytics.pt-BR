---
description: Requisitos de sistema e comparação da Analysis Workspace, Reports & Analytics, Ad Hoc Analysis, Report Builder Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
translation-type: tm+mt
source-git-commit: 9265fb410b20a764ecc86c56b453b045122fcd05
workflow-type: tm+mt
source-wordcount: '689'
ht-degree: 76%

---


# Analytics Comparação e requisitos de produtos do 

Requisitos de sistema e comparação da Analysis Workspace, Reports &amp; Analytics, Ad Hoc Analysis, Report Builder Data Warehouse e Data Workbench.

Para obter informações sobre qual produto Adobe Analytics usar, acesse [aqui](/help/admin/c-analytics-product-comparison/which-analytics-tool.md).

| Nome do produto e link de ajuda | [Analysis Workspace](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html) | [Reports &amp; Analytics](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/reports-analytics/getting-started.html) | [Ad Hoc Analysis](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/ad-hoc-analysis/adhoc-home.html) | [Report Builder](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/home.html) | [Data Warehouse](https://docs.adobe.com/content/help/pt-BR/analytics/export/data-warehouse/data-warehouse.translate.html) | [Data Workbench](https://docs.adobe.com/content/help/pt-BR/data-workbench/using/home.html) |
|---|---|---|---|---|---|---|
| **Método de acesso** | Solução de navegador para desenvolver projetos de análise avançados e personalizados, bem como para democratizar informações. | Solução de navegador para análise digital. | Ferramenta em Java para análises digitais avançadas. | Suplemento do Excel que permite a criação de solicitações personalizadas de dados de R&amp;A e a visualização usando o Microsoft Excel. | Solução de navegador que gera relatórios no formato .csv. Pode gerar arquivos no formato Tableau. | Ferramenta de análise multicanal para análises avançadas, como modelo de atribuição personalizado, análise preditiva e análise completa do cliente. |
| **Detalhamento de relatórios** | Ilimitado | Até 2 correlações | Ilimitado | Até 2 correlações | Executa detalhamentos expandidos e ilimitados, detalhamento por segmento. | Ilimitado |
| **Comparação de segmentos** | Ilimitado | Até 2 segmentos | Ilimitado | Ilimitada (pilha de solicitação de dados) | 1 segmento. Suporte a diversos segmentos (empilhados). | Ilimitado |
| **Limite de saída da linha** | 400 | 200 | 50.000 | 50.000 | Ilimitado | Personalizável |
| **** Limites de valor únicos (nos relatórios de eVar/prop) | 500 K-2 MM | 500 K-2 MM | 500 K-2 MM | 500 K-2 MM | Ilimitado | Personalizável |
| **Afunilamento/Caminhos** | Sim: [Fallout](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html)/[Fluxo](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/flow/flow.html) | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/reports.html) | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-reports-paths.html) | Sim | Não | Sim |
| **Análise avançada da jornada do cliente** | Yes: [Customer Journey Analytics](https://docs.adobe.com/content/help/pt-BR/analytics-platform/using/cja-landing.html) | Não | Sim | Não | Não | Sim |
| **Análise de coorte** | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.html) | Não | Não | Não | Não | Sim |
| **Atribuição avançada** | [Attribution IQ](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/attribution-iq.html) | Limitado - primeiro/último/linear | Limitado - primeiro/último/linear | Limitado - primeiro/último/linear | Limitado - primeiro/último/linear | Sim |
| **Opções de visualização melhoradas** | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html) | Não | Sim | Sim | Não | Sim |
| **Layout personalizado** | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/home.html) | Sim - [Painéis](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/dashboard.html) | Não | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/configure-the-custom-layout.html) | Classifique os resultados por detalhamento ou por métricas. | Sim |
| **** Organização de projeto (simplifique relatórios para não analistas) | [Sim](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html) | Não | Não | Sim | Não | Sim |
| **Compartilhamento de projeto** | [Sim: todos/todos os usuários](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/curate-share/curate.html) | [Sim: todos/todos os usuários](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | Somente com usuários da Ad Hoc Analysis | Sim: todos/todos os usuários | Não | Sim |
| **Delivery de relatório** agendado | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/curate-share/schedule-projects.html) | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/scheduling.html) | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-schedule.html) | [Sim](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/t-schedule-a-data-request.html) | Sim | Sim |
| **Requisitos de sistema** | <br>[NavegadorMais...](https://docs.adobe.com/content/help/pt-BR/analytics/admin/sys-reqs.html) | <br>[NavegadorMais...](https://docs.adobe.com/content/help/pt-BR/analytics/admin/sys-reqs.html) | <br>[JavaMais...](https://docs.adobe.com/content/help/en/analytics/analyze/ad-hoc-analysis/c-getting-started.html) | Windows, MS<br>[ExcelMais...](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/report-builder/report-builder-setup/system-requirements.html) | Navegador e programa para abrir arquivos .csv como MS Excel. Pode gerar arquivos no formato Tableau. | Windows 64 bit, good graphics adapter for OpenGL 3.2 [More...](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html) |
| **Compatibilidade do Conjunto de relatórios virtuais (processamento de tempo do relatório)** | Sim | Sim | Sim | Sim | Não | Sim? |
| **Múltiplos Conjuntos de relatórios** | Sim | Não | Não | Não | Não | Sim? |
| **Métricas calculadas** | Sim | Sim | Sim | Sim | Sim | Sim |
| **Compatibilidade do Canal de marketing** | Sim | Sim | Sim | Sim | ? | ? |
| **Nível de granularidade** |  |  |  |  |  |  |
| **Detecção de anomalias** | Sim | Não |  |  |  |  |
| **Análise de contribuição** | Sim | Não | Não | Não | Não | Sim |
| **Tipos de segmento** |  |  |  |  |  |  |