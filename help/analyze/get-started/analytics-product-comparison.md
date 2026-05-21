---
description: Requisitos de sistema e comparação do Analysis Workspace, Reports Builder, Data Warehouse e Data Workbench
title: Comparação e requisitos de produtos do Analytics
exl-id: 5adc6c10-cbbb-48d5-a7ab-367cbaff5e8a
feature: Analytics Basics
TQID: https://experienceleague.adobe.com/VQgK6DUSlz-UA3zk-Q18-QOAI5M6xfK7KqBYwW56j6w
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: a421fb65-2c82-457a-921c-28c46b697a39
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: af53ada8-1b7d-4929-ac91-ac971dd20ec7
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
  - id: c4cb071e-4667-4fb1-b1f1-d8994549cfb2
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e9cb007b-c8b7-4975-bc81-11a788c535fa
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 67%

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
| **Nível de processamento** | Totalmente processado | Totalmente processado, com [relatório em tempo real](/help/admin/tools/manage-rs/edit-settings/realtime/realtime.md) separado | Totalmente processado | Totalmente processado | Totalmente processado |
| **Inclusão dos dados do filtro de bot do administrador** <br> [Saiba mais](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-removal.md) | Não | Sim - relatório de bot separado | Não | Não | Não |
| **Baixo tráfego (únicos excedidos) aparece** <br> [Saiba mais](/help/technotes/low-traffic.md) | Sim | Sim | Não | Não | Sim |
| **Limite de linha visível (antes da paginação)** | 400 | 50000 | Ilimitado | Ilimitado | 50000 |
| **Vários conjuntos de relatórios** | [Sim](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) | Sim | Não | Sim | Não |
| **Quantidade de detalhamentos** | Ilimitado | Até 2 | Ilimitado | Ilimitado | Ilimitado, executar em vários queries |
| **Segmentação** <br> [Saiba mais](/help/components/segmentation/segmentation-workflow/seg-workflow.md) | Sim | Sim | Sim, com [limitações](/help/components/segmentation/seg-reference/seg-compatibility.md) | Não | Sim |
| **Métricas calculadas** <br> [Saiba mais](/help/components/calculated-metrics/cm-overview.md) | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Sim, com Atribuição | Sim | Não | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Canais de marketing** <br> [Saiba mais](/help/components/c-marketing-channels/c-getting-started-mchannel.md) | Sim | Sim | Sim | Sim - [va_finder, va_closer](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) | Sim |
| **Análise de coorte** | [Sim](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Sim | Não | Não | Não |
| **Atribuição** | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) | Limitado | Não | Não | Sim, com o [Attribution](/help/analyze/analysis-workspace/attribution/overview.md) |
| **Preparação** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/curate.md) | Sim: conjunto de relatórios de projeto e virtuais | Não | Não | Não | Sim: somente conjunto de relatórios virtuais |
| **Compartilhamento de projeto** <br> [Saiba mais](/help/analyze/analysis-workspace/curate-share/share-projects.md) | Sim, com funções de projeto | Sim | Não | Não | Não |
| **Delivery programado** | Sim | Sim | Sim | Sim | Não |
| **Destinos do delivery** | Email | Email, FTP, SFTP, [publicação no Microsoft Power BI](/help/analyze/legacy-report-builder/c-publish-power-bi/power-bi.md) | Amazon S3, Google Cloud Platform, Azure SAS, Azure RBAC e Email | Amazon S3, Azure RBAC, Azure SAS e Google Cloud Platform | - |
| **Processamento de tempo de relatório do conjunto de relatórios virtuais** <br> [Saiba mais](/help/components/vrs/vrs-report-time-processing.md) | Sim | Não | Não | Não | Sim |
| **Relatórios de geografia e tecnologia** | Sim <p>Usa valores médios em vez de campos de publicação. A lógica de primeira ocorrência é baseada em `post_cust_hit_time_gmt` em vez de `visit_page_num=1`. Os resultados podem diferir de outras ferramentas se o IP for alterado no meio da visita, as ocorrências chegarem fora de ordem ou as visitas cruzarem os limites do mês.</p> | Sim <p>Usa valores médios em vez de campos de publicação. A lógica de primeira ocorrência é baseada em `post_cust_hit_time_gmt` em vez de `visit_page_num=1`. Os resultados podem diferir de outras ferramentas se o IP for alterado no meio da visita, as ocorrências chegarem fora de ordem ou as visitas cruzarem os limites do mês.</p> | Sim <p>Usa valores de postagem e `visit_page_num=1` para determinar a primeira ocorrência da visita. Aplica o valor da primeira ocorrência a todas as ocorrências na visita para essas dimensões.</p> | Sim <p>Usa valores de postagem e `visit_page_num=1` para determinar a primeira ocorrência da visita. Aplica o valor da primeira ocorrência a todas as ocorrências na visita para essas dimensões.</p> | Sim <p>Usa valores médios em vez de campos de publicação. A lógica de primeira ocorrência é baseada em `post_cust_hit_time_gmt` em vez de `visit_page_num=1`. Os resultados podem diferir de outras ferramentas se o IP for alterado no meio da visita, as ocorrências chegarem fora de ordem ou as visitas cruzarem os limites do mês.</p> |
