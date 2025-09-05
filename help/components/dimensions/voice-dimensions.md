---
title: Dimensões de análise de voz
description: Dimensões de análise de voz
feature: Dimensions
exl-id: 6e1275c4-3b17-4c65-a308-d420ea1acdf6
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '133'
ht-degree: 4%

---

# Dimensões de análise de voz

Quando você habilita o [!UICONTROL Voice and Chatbots] no [[!UICONTROL Application reporting]](/help/admin/tools/manage-rs/edit-settings/app-reporting.md), as seguintes dimensões (e [métricas](../metrics/voice-metrics.md)) são criadas. Você pode usar [Variáveis de dados de contexto](/help/implement/vars/page-vars/contextdata.md) para defini-las com o valor da cadeia de caracteres desejado. Quando habilitadas nas configurações do conjunto de relatórios, as [Regras de processamento](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md) são criadas automaticamente para mapear dimensões de análise de voz para a variável de dados de contexto associada.

| Nome da dimensão | Descrição | Variável de dados de contexto |
| --- | --- | --- |
| Tipo de Erro de Voz | O tipo de erro encontrado. | `a.voiceerrortype` |
| Idioma de voz | O idioma em que o usuário interage com o aplicativo de voz. | `a.voicelanguage` |
| Intenção de voz | O comando que o usuário pretende executar. | `a.voiceintent` |
| Resposta do aplicativo de voz | A resposta que o aplicativo de voz retornou ao usuário. | `a.voiceappresponse` |
| Autenticação de voz | O estado autenticado do usuário ao interagir com o aplicativo de voz. | `a.voiceauthentication` |
| ID do ponto de interesse | A ID do ponto de interesse. | `a.loc.poi.id` |

{style="table-layout:auto"}
