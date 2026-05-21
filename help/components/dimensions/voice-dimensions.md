---
title: Dimensões de análise de voz
description: Dimensões de análise de voz
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
TQID: https://experienceleague.adobe.com/OZ-lQkbS8hsv8ywUUa2BQoH40nfklRkJNd9SlEVkmEI
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
source-wordcount: 133
ht-degree: 16%

---

# Dimensões de análise de voz

Quando você habilita o [!UICONTROL Voice and Chatbots] no [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), as seguintes dimensões (e [métricas](../metrics/voice-metrics.md)) são criadas. Você pode usar [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para defini-las com o valor da cadeia de caracteres desejado. Quando habilitadas nas configurações do conjunto de relatórios, as [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) são criadas automaticamente para mapear dimensões de análise de voz para a variável de dados de contexto associada.

| Nome da dimensão | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| Tipo de erro de voz | O tipo de erro encontrado. | `a.voiceerrortype` |
| Idioma da voz | O idioma em que o usuário interage com o aplicativo de voz. | `a.voicelanguage` |
| Propósito de voz | O comando que o usuário pretende executar. | `a.voiceintent` |
| Resposta do aplicativo de voz | A resposta que o aplicativo de voz retornou ao usuário. | `a.voiceappresponse` |
| Autenticação de voz | O estado autenticado do usuário ao interagir com o aplicativo de voz. | `a.voiceauthentication` |
| ID do ponto de interesse | A ID do ponto de interesse. | `a.loc.poi.id` |

{style="table-layout:auto"}
