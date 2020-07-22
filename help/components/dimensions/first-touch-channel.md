---
title: canal de primeiro toque
description: O primeiro canal de marketing dentro da expiração do envolvimento do visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---


# canal de primeiro toque

A dimensão &#39;canal de primeiro toque&#39; relata o primeiro canal de marketing com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego inicial para o seu site, permitindo que você concentre esforços de marketing em áreas mais eficazes.

## Preencher esta dimensão com dados

Essa dimensão faz referência diretamente aos nomes dos canais que você definiu no gerenciador [](/help/admin/admin/marketing-channels-admin.md)de canais de marketing.

Cada ocorrência enviada para os servidores de coleta de dados da Adobe é executada pelas regras de processamento de canais de marketing do conjunto de relatórios. Ele repete cada regra em ordem numérica até encontrar uma correspondência, na qual o canal de marketing se vincula à ocorrência. O canal de primeiro toque persiste com o visitante até que ele não visite o site por mais tempo do que o período de envolvimento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão para um valor específico, as seguintes etapas serão necessárias:

* Defina o item de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canais de marketing que contenha os critérios desejados para a ocorrência.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de Marketing _e,_ para isso, deve ser o primeiro valor do canal de marketing no período de envolvimento do visitante.

Se uma ocorrência subsequente corresponder aos critérios em um canal de marketing diferente, essa dimensão não será substituída pelo novo canal de marketing.

## Itens de dimensão

Os itens de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, que afetam os valores dessa dimensão.
