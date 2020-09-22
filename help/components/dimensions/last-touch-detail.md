---
title: Detalhes do canal de último contato
description: Detalhes do canal de marketing mais recente dentro da expiração do engajamento do visitante.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '313'
ht-degree: 100%

---


# Detalhes do canal de último contato

Os detalhes da dimensão &quot;Detalhes do canal de último contato&quot; oferecem informações sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento (30 dias por padrão). Essa dimensão é importante para entender o que contribuiu para a correspondência em um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.

## Preencher esta dimensão com dados

Essa dimensão copia valores de outras variáveis. A variável utilizada se refere ao valor do canal de cada [Regra de processamento de canal de marketing](/help/admin/admin/marketing-channels-admin.md). Quando uma ocorrência corresponde a uma regra de processamento de canal de marketing, a dimensão [Canal de último contato](last-touch-channel.md) é definida como o nome do canal e essa dimensão é definida como o valor do canal definido na regra.

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Verifique se o item de dimensão desejado está em um atributo de ocorrência ou em uma variável personalizada.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* Selecione o valor desejado na lista suspensa em [!UICONTROL Definir o valor do canal] na regra de processamento Canal de marketing.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

## Itens de dimensão

Os itens de dimensão dependem da lista suspensa de valores do canal. Por exemplo, se você definir o valor do canal como “URL da página”, os itens de dimensão incluirão URLs de página no site. Se você definir o valor do canal como Domínio de referência, os itens de dimensão incluirão domínios nos quais os visitantes clicaram para acessar seu site. Essa dimensão agrega todos os itens de dimensão de detalhes, independentemente do canal em que estão.

A Adobe recomenda definir valores de canal relacionados ao canal de marketing para obter informações sobre os detalhes do canal.
