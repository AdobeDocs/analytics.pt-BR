---
title: Canal de último contato
description: O canal de marketing mais recente durante o período de envolvimento do visitante.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '250'
ht-degree: 100%

---


# Canal de último contato

A dimensão “Canal de último contato” informa o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento do visitante (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões, permitindo que você concentre esforços de marketing em áreas mais eficientes.

## Preencher esta dimensão com dados

Essa dimensão faz referência diretamente aos nomes dos canais que você definiu no [Gerenciador de canais de marketing](/help/admin/admin/marketing-channels-admin.md).

Cada ocorrência enviada para os servidores de coleta de dados da Adobe é executada pelas regras de processamento do canal de marketing do conjunto de relatórios. Ela repete cada regra em ordem numérica até encontrar uma correspondência em que o canal de marketing se vincula à ocorrência. O canal de último contato persiste com o visitante até que ele não visite o site por mais tempo do que o período de engajamento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Defina o item de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

## Itens de dimensão

Os itens de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, o que afetará os valores dessa dimensão.
