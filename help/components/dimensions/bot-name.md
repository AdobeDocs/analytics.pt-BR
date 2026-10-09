---
title: Nome do bot
description: O nome do bot que correspondeu às Regras de bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: 'https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 7a99ecd99a9b1a639c8a2d48dc35d57fdfeb1a12
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 10%
---
# Nome do bot

A [dimensão](overview.md) de &#39;Nome de bot&#39; mostra os nomes de bots que foram detectados usando as [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). Essas regras podem ser regras IAB padrão ou regras de bot personalizadas configuradas pela organização. É útil nos casos em que você deseja saber mais sobre quais bots estão visitando seu site ou quais bots geram mais tráfego.

As ocorrências que correspondem a [!UICONTROL Regras de bot] são automaticamente filtradas de todos os relatórios do Analytics, com exceção a esta dimensão, [Ocorrências de bot](../metrics/bot-occurrences.md), [Exibições de página de bot](../metrics/bot-page-views.md) e [Ocorrências de produto de bot](../metrics/bot-product-occurrences.md). É possível utilizar essa dimensão e essas três métricas para ver quais dados de bot são excluídos do restante dos relatórios.

Como os relatórios de bot são separados do restante dos dados do conjunto de relatórios, somente as seguintes dimensões e métricas são compatíveis com essa dimensão:

* [Página](page.md)
* Dimensões com base em tempo (por exemplo, [Dia](day.md), [Semana](week.md) ou [Mês](month.md))
* [Ocorrências de bot](../metrics/bot-occurrences.md)
* [Exibições de página de bot](../metrics/bot-page-views.md)
* [Ocorrências de produto de bot](../metrics/bot-product-occurrences.md)

Usar qualquer outra dimensão ou métrica com essa dimensão não retorna dados.

## Preencher esta dimensão com dados

Se você tiver habilitado [Regras de bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), esta dimensão coletará dados automaticamente. Se você ainda não tiver habilitado as [!UICONTROL Regras de bot], esta dimensão não aparecerá no Analysis Workspace.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado de regras de detecção de bot) |
| **Web SDK / campo XDM** | Nenhum (derivado de regras de detecção de bot) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | N/D |

## Itens de dimensão

Cada item de dimensão lista o nome do bot que correspondeu aos critérios da IAB ou da regra de bot personalizada.
