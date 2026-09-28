---
description: Visão geral do fluxo de trabalho do Advertising Analytics.
title: Visão geral do fluxo de trabalho
feature: Advertising Analytics
exl-id: 00993c19-1e74-4a97-b16a-967feab13b32
TQID: 'https://experienceleague.adobe.com/Xrm-gn59uSRzBKtwY1Z6O40b7d0MS-LH-Y96hLjbJKQ'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
    internal-label: Advertising integration
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
    internal-label: Advertising Analytics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 42%
---
# Visão geral do fluxo de trabalho

O fluxo de trabalho de configuração do Advertising Analytics consiste nas seguintes etapas:

<!--
>[!VIDEO](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/integrations/ad-cloud/configuring-advertising-analytics)
-->

1. [Habilitar relatórios do Advertising Analytics por conjunto de relatórios](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-provision-rs.md). Habilite os relatórios do [!UICONTROL Advertising Analytics] para conjuntos de relatórios habilitados pela Experience Cloud.
2. [Configurar uma conta do Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-create-ad-account.md). Configuração nas Ferramentas administrativas do Analytics.
3. [Relatório de dados de publicidade no Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-report-ad-data-an.md). Os dados de pesquisa são extraídos dos mecanismos de pesquisa por volta das 6h00 no fuso horário de seu data center do Adobe Analytics. Os dados do Adobe Advertising são coletados e inseridos no conjunto de relatórios. Em seguida, é convertido no fuso horário do conjunto de relatórios como parte da inserção de dados no Analytics. Os relatórios estão disponíveis no Analysis Workspace (modelo de Pesquisa de desempenho pago), Report Builder e na API de relatórios do Analytics.
4. [Gerenciar contas publicitárias](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md). É possível verificar o status da conta, além de editar/pausar contas.
