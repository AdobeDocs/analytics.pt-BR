---
title: Detalhes do canal de último contato
description: Detalhes do canal de marketing mais recente dentro da expiração do engajamento do visitante.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
TQID: https://experienceleague.adobe.com/bVZVCTQQ1tZVB0qF9fxeCU1Ec6bjcspymoyOY-AQATU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 80%

---

# Detalhes do canal de último contato

O &quot;Detalhe do canal de último contato&quot; [dimensão](overview.md) relata detalhes sobre o canal de marketing mais recente com o qual um visitante corresponde durante o período de engajamento (30 dias por padrão). Essa dimensão é importante para entender o que contribuiu para a correspondência em um canal de marketing. Por exemplo, se um visitante chegasse ao seu site e correspondesse ao canal de marketing &quot;Pesquisa paga&quot;, você poderia usar os detalhes do canal para ver qual mecanismo de pesquisa foi usado ou qual palavra-chave foi pesquisada.

## Preencher esta dimensão com dados

Essa dimensão copia valores de outras variáveis. A variável utilizada se refere ao valor do canal de cada [Regra de processamento de canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Quando uma ocorrência corresponde a uma regra de processamento de canal de marketing, a dimensão [Canal de último contato](last-touch-channel.md) é definida como o nome do canal e essa dimensão é definida como o valor do canal definido na regra.

Se você quiser definir essa dimensão com um valor específico, siga os seguintes passos:

* Verifique se o item de dimensão desejado está em um atributo de ocorrência ou em uma variável personalizada.
* Defina uma regra de processamento de canal de marketing que contenha os critérios desejados para a ocorrência.
* Selecione o valor desejado na lista suspensa em [!UICONTROL Definir o valor do canal] dentro da regra de processamento Canal de marketing.
* A ocorrência do visitante em seu site deve corresponder aos critérios descritos na regra de processamento do canal de marketing.

## Itens de dimensão

Os itens do Dimension dependem do valor do canal listado na lista suspensa para a regra de processamento de canal de marketing aplicável. Por exemplo, se você definir o valor do canal como “URL da página”, os itens de dimensão incluirão URLs de página no site. Se você definir o valor do canal como Domínio de referência, os itens de dimensão incluirão domínios nos quais os visitantes clicaram para acessar seu site. Essa dimensão agrega todos os itens de dimensão de detalhes, independentemente do canal em que estão.

A Adobe recomenda definir valores de canal relacionados ao canal de marketing para obter informações sobre os detalhes do canal.
