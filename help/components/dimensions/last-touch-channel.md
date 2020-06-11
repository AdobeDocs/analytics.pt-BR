---
title: canal de último toque
description: O canal de marketing mais recente dentro da expiração do envolvimento do visitante.
translation-type: tm+mt
source-git-commit: 2c262e5345c39a71a6a54062c607273528294b24
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---


# canal de último toque

A dimensão &#39;canal de último toque&#39; relata o canal de marketing mais recente com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão). Essa dimensão é importante para entender quais canais de marketing direcionam o tráfego para o seu site que resulta em conversões, permitindo que você concentre esforços de marketing em áreas mais eficazes.

## Preencher esta dimensão com dados

Essa dimensão faz referência diretamente aos nomes dos canais que você definiu no gerenciador [](/help/admin/admin/marketing-channels-admin.md)de canais de marketing.

Cada ocorrência enviada para os servidores de coleta de dados da Adobe é executada pelas regras de processamento de canais de marketing do conjunto de relatórios. Ele repete cada regra em ordem numérica até encontrar uma correspondência, na qual o canal de marketing se vincula à ocorrência. O último canal de toque persiste com o visitante até que ele não visite o site por mais tempo do que o período de envolvimento do visitante (30 dias por padrão).

Se você quiser definir essa dimensão para um valor específico, as seguintes etapas serão necessárias:

* Defina o valor de dimensão desejado como um canal no Gerenciador de canais de marketing em Configurações do conjunto de relatórios.
* Defina uma regra de processamento de canais de marketing que contenha os critérios desejados para a ocorrência.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

## Valores de dimensão

Os valores de dimensão incluem qualquer nome de canal no Gerenciador de canais de marketing. Por padrão, os valores incluem `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`e `"Referring domains"`. Você pode adicionar ou excluir canais no Gerenciador de canais de marketing, que afetam os valores dessa dimensão.
