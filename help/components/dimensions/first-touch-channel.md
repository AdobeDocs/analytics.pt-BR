---
title: Canal de primeiro contato
description: O primeiro canal de marketing dentro da expiração do engajamento do visitante.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 91%

---

# Canal de primeiro contato

A [dimensão](overview.md) do &quot;Canal de primeiro contato&quot; informa o primeiro canal de marketing com o qual um visitante corresponde durante o período de engajamento (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego inicial para o seu site, permitindo que você concentre esforços de marketing em áreas mais eficientes.

## Preencher esta dimensão com dados

Essa dimensão faz referência diretamente aos nomes dos canais que você definiu no [Gerenciador de canais de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Cada ocorrência enviada para os servidores de coleta de dados da Adobe é executada pelas regras de processamento do canal de marketing do conjunto de relatórios. Ela repete cada regra em ordem numérica até encontrar uma correspondência em que o canal de marketing se vincula à ocorrência. O canal de primeiro contato persiste com o visitante até que ele não visite o site por mais tempo do que o período de engajamento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Defina o item de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* A ocorrência do visitante no site deve corresponder aos critérios descritos na regra de processamento Canal de marketing _e_ deve ser o primeiro valor do canal de marketing a fazer isso durante o período de engajamento do visitante.

Se uma ocorrência subsequente corresponder aos critérios em um canal de marketing diferente, essa dimensão não será substituída pelo novo canal de marketing.

## Itens de dimensão

Os itens de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, o que afetará os valores dessa dimensão.
