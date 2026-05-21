---
title: Métricas de análise de voz
description: Métricas de análise de voz
feature: Metrics
exl-id: 3c1b4e4e-d8d2-446f-9582-a2ce5580a8d3
TQID: https://experienceleague.adobe.com/snDtqM3TiX--cjPjKj8cGkaFxMIxRprvD4ia9OnBXJk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 102
ht-degree: 21%

---

# Métricas de análise de voz

Quando você habilita o [!UICONTROL Voice and Chatbots] no [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), as seguintes métricas (e [dimensões](../dimensions/voice-dimensions.md)) são criadas. Você pode usar [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para defini-las com um valor de `1` (ou mais, se aplicável). Quando habilitadas nas configurações do conjunto de relatórios, as [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) são criadas automaticamente para mapear métricas de análise de voz para a variável de dados de contexto associada.

| Nome da métrica | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| Enunciados de voz | Dispara quando um comando é emitido para um assistente de voz. | `a.voiceutterances` |
| Sessão de fim de voz | Acionado quando o aplicativo de voz é fechado. | `a.voiceendsession` |
| Erro de voz | Acionado quando o aplicativo de voz encontra um erro. | `a.voiceerror` |

{style="table-layout:auto"}
