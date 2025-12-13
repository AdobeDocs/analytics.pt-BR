---
title: Canal de último contato
description: O canal de marketing mais recente durante o período de engajamento do visitante.
feature: Dimensions
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
source-git-commit: 31c3f83f1142a4ba92a390e35ca8dcae66dfa660
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 67%

---

# Canal de último contato

O &quot;Canal de último contato&quot; [dimensão](overview.md) informa o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões, permitindo que você concentre esforços de marketing em áreas mais eficientes.

## Preencher esta dimensão com dados

Essa dimensão faz referência diretamente aos nomes dos canais que você definiu no [Gerenciador de canais de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-channels.md).

Cada ocorrência enviada para os servidores de coleta de dados da Adobe é executada pelas regras de processamento do canal de marketing do conjunto de relatórios. Ela repete cada regra em ordem numérica até encontrar uma correspondência em que o canal de marketing se vincula à ocorrência. O canal de último contato persiste com o visitante até que ele não visite o site por mais tempo do que o período de engajamento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Defina o item de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

>[!TIP]
>
>O uso desta dimensão com métricas que usam a [atribuição de participação](/help/analyze/analysis-workspace/attribution/models.md) pode atribuir crédito a `None` quando outros modelos de atribuição não o fazem. As métricas de participação exigem uma [instância](../metrics/instances.md) do canal de marketing dentro da janela de relatórios para receber crédito. Se o canal de marketing foi definido inicialmente fora da janela de relatórios e apenas o valor persistente existe dentro da janela de relatórios, as métricas de participação atribuem crédito a `None`. Outros modelos de atribuição atribuem crédito ao valor persistente. Caso deseje evitar a atribuição a `None` neste cenário, considere usar um modelo de atribuição de não participação.

## Itens de dimensão

Os itens de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, o que afetará os valores dessa dimensão.
