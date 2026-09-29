---
title: Canal de último contato
description: O canal de marketing mais recente durante o período de engajamento do visitante.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
TQID: 'https://experienceleague.adobe.com/wUNsv-0snBfk6EE6yeCEuT8-hGvBu9U8tjKDfxhVRA0'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
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
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '375'
ht-degree: 49%
---
# Canal de último contato

O &quot;Canal de último contato&quot; [dimensão](overview.md) informa o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões, permitindo que você concentre esforços de marketing em áreas mais eficientes.

## Preencher esta dimensão com dados

Essa dimensão é derivada pelas Regras de processamento de canal de marketing. Ele faz referência diretamente aos nomes dos canais que você definiu no [Gerenciador de canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md). Cada ocorrência passa pelas regras de processamento do canal de marketing do conjunto de relatórios em ordem numérica até encontrar uma correspondência, que vincula esse canal de marketing à ocorrência. Não há variável a ser definida.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (derivado das regras de processamento do Canal de marketing) |
| **Web SDK / campo XDM** | Nenhum (derivado das regras de processamento do Canal de marketing) |
| **Parâmetro de consulta** | N/D |
| **Marca XML** | N/D |
| **Limite de bytes** | N/D |
| **Persistência** | Configurável |

O canal de último contato persiste com o visitante até que ele não visite o site por mais tempo do que o período de engajamento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Defina o item de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* O hit do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

>[!TIP]
>
>O uso desta dimensão com métricas que usam a [atribuição de participação](/help/analyze/analysis-workspace/attribution/models.md) pode atribuir crédito a `None` quando outros modelos de atribuição não o fazem. As métricas de participação exigem uma [instância](../metrics/instances.md) do canal de marketing dentro da janela de relatórios para receber crédito. Se o canal de marketing foi definido inicialmente fora da janela de relatórios e apenas o valor persistente existe dentro da janela de relatórios, as métricas de participação atribuem crédito a `None`. Outros modelos de atribuição atribuem crédito ao valor persistente. Caso deseje evitar a atribuição a `None` neste cenário, considere usar um modelo de atribuição de não participação.

## Itens de dimensão

Os itens de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, o que afetará os valores dessa dimensão.
