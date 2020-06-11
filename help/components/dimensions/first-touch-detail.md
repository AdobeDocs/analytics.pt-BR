---
title: Detalhes do canal de primeiro toque
description: Detalhes do primeiro canal de marketing dentro da expiração do envolvimento do visitante.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 0%

---


# Detalhes do canal de primeiro toque

A dimensão &quot;Detalhes do canal de primeiro toque&quot; relata detalhes sobre o primeiro canal de marketing com o qual um visitante corresponde durante o período de envolvimento do visitante (30 dias por padrão). Essa dimensão é importante para entender o que contribuiu para a ocorrência correspondente a um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de Marketing de &#39;Pesquisa paga&#39;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave eles procuraram.

## Preencher esta dimensão com dados

Essa dimensão copia valores de outras variáveis. A variável usada faz referência ao valor do canal em cada regra [de processamento do](/help/admin/admin/marketing-channels-admin.md)canal de marketing. Quando uma ocorrência corresponde a uma regra de processamento de canal de marketing, a dimensão de canal [de](last-touch-channel.md) último toque é definida como o nome do canal e essa dimensão é definida como o valor do canal definido na regra.

Se você quiser definir essa dimensão para um valor específico, as seguintes etapas serão necessárias:

* Verifique se o valor de dimensão desejado está em um atributo de ocorrência ou variável personalizada.
* Defina uma regra de processamento de canais de marketing que contenha os critérios desejados para a ocorrência.
* Selecione o valor suspenso desejado em [!UICONTROL Definir o valor] do canal na regra de processamento do canal de Marketing.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing _e_ deve ser o primeiro valor do canal de marketing para fazer isso no período de envolvimento do visitante.

Se uma ocorrência subsequente corresponder aos critérios em um canal de marketing diferente, essa dimensão não será substituída pelo novo canal de marketing.

## Valores de dimensão

Os valores de dimensão dependem da lista suspensa de valores do canal. Por exemplo, se você definir o valor do canal como &quot;URL da página&quot;, os valores de dimensão incluirão URLs de página no site. Se você definir o valor do canal como Domínio de referência, os valores de dimensão incluirão domínios pelos quais os visitantes clicaram para chegar ao site. Essa dimensão agregação todos os valores de dimensão de detalhes, independentemente do canal em que estão.

A Adobe recomenda definir valores de canal relacionados ao canal de marketing para obter informações sobre detalhes do canal.
