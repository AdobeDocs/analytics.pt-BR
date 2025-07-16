---
title: Métricas de análise de voz
description: Métricas de análise de voz
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
source-git-commit: c2adf6d2e328378332cc290ba2dfd75ee6587ef6
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 21%

---

# Métricas de análise de voz

Quando você habilita o [!UICONTROL Voice and Chatbots] no [[!UICONTROL Application reporting]](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/app-reporting.md), as seguintes métricas (e [dimensões](../dimensions/voice-dimensions.md)) são criadas. Você pode usar [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para defini-las com um valor de `1` (ou mais, se aplicável). Quando habilitadas nas configurações do conjunto de relatórios, as [Regras de processamento](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/processing-rules/pr-overview.md) são criadas automaticamente para mapear métricas de análise de voz para a variável de dados de contexto associada.

| Nome da métrica | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| Enunciados de voz | Dispara quando um comando é emitido para um assistente de voz. | `a.voiceutterances` |
| Sessão de fim de voz | Acionado quando o aplicativo de voz é fechado. | `a.voiceendsession` |
| Erro de voz | Acionado quando o aplicativo de voz encontra um erro. | `a.voiceerror` |

{style="table-layout:auto"}
