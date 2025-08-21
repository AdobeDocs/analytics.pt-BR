---
title: Fontes de dados de IDs de transação
description: Use valores armazenados de uma ocorrência online para enriquecer ocorrências offline que compartilhem uma ID de transação.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 0a65114d598b7c6d2871a2446ad4d574b9ca44bb
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 8%

---

# Fontes de dados de IDs de transação

As fontes de dados de ID de transação são uma variação das fontes de dados de resumo que permitem aplicar valores salvos de uma ocorrência online a linhas offline que compartilham a mesma ID de transação. Essa abordagem é útil quando você captura uma transação on-line, mas recebe detalhes posteriormente de outro sistema. Os principais exemplos incluem devoluções de produtos, cancelamentos de reserva ou resultados de interações da central de atendimento.

>[!NOTE]
>
>Antes de usar fontes de dados de ID de transação, você deve primeiro habilitá-lo em [Configurações Gerais da Conta](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) para o conjunto de relatórios desejado.

## Como funciona

O conceito de IDs de transação requer duas partes:

* **Ocorrência online**: qualquer ocorrência completa do Analytics enviada para um conjunto de relatórios (AppMeasurement, Web SDK, API etc.). Nesta ocorrência, você define a variável de implementação [`transactionID`](/help/implement/vars/page-vars/transactionid.md).
* **Ocorrência offline**: uma linha carregada por meio de fontes de dados. No arquivo, inclua a coluna `transactionID` com um valor que corresponda a uma ocorrência online.

Ao enviar uma ocorrência online que contém a variável de implementação `transactionID`, o Adobe faz um &quot;instantâneo&quot; das seguintes dimensões que foram definidas ou mantidas até o momento:

* [Categoria](/help/components/dimensions/category.md)
* [Dias antes da primeira compra](/help/components/dimensions/days-before-first-purchase.md)
* [Dias desde a última compra](/help/components/dimensions/days-since-last-purchase.md)
* [eVars 1-250](/help/components/dimensions/evar.md)
* Dimensões específicas de recursos habilitadas nas [configurações do conjunto de relatórios](/help/admin/admin/c-manage-report-suites/report-suites-admin.md) que se comportam de forma semelhante às eVars. As dimensões específicas de recursos que se comportam de forma semelhante às props não são incluídas.
* [Variáveis da Lista](/help/implement/vars/page-vars/list.md)
* [Canal de marketing](/help/components/dimensions/marketing-channel.md)
* [Detalhes do canal de marketing](/help/components/dimensions/marketing-detail.md)
* [Dimensões móveis](/help/components/dimensions/mobile-dimensions.md)
* [Domínio referenciador original](/help/components/dimensions/original-referring-domain.md)
* [Produto](/help/components/dimensions/product.md)
* [Domínio de referência](/help/components/dimensions/referring-domain.md)
* [Mecanismo de pesquisa](/help/components/dimensions/search-engine.md)
* [Palavra-chave de pesquisa](/help/components/dimensions/search-keyword.md)
* [Código de rastreamento](/help/components/dimensions/tracking-code.md)
* [Número da visita](/help/components/dimensions/visit-number.md)

>[!NOTE]
>
>Métricas (como [Pedidos](/help/components/metrics/orders.md) ou [Eventos personalizados](/help/components/metrics/custom-events.md)) não estão incluídas no &quot;instantâneo&quot;.

Ao fazer upload de uma ocorrência offline por meio de fontes de dados que contém uma ID de transação correspondente, todas as dimensões disponíveis no &quot;instantâneo&quot; são automaticamente anexadas à linha da fonte de dados. Se uma determinada dimensão estiver presente na ocorrência online e offline, o valor da ocorrência offline será usado.

>[!IMPORTANT]
>
>O conceito de fontes de dados de ID de transação ajuda a preencher apenas as linhas da fonte de dados (ocorrências offline). Eles não afetam ou alteram a ocorrência online.

## Considerações sobre a fonte de dados da ID de transação

As fontes de dados de ID de transação têm as seguintes propriedades:

* Os dados online devem ser coletados e processados primeiro. Se uma fonte de dados de ID de transação for carregada antes de um conjunto de relatórios processar uma ocorrência correspondente a essa ID de transação, os dados serão tratados como uma fonte de dados de resumo.
* As IDs de transação coletadas de ocorrências online expiram após 25 meses.
* As fontes de dados carregadas com uma ID de transação expirada são tratadas de forma semelhante aos dados carregados sem uma ID de transação.
* Se você definir a mesma ID de transação em várias ocorrências online, somente o &quot;instantâneo&quot; da primeira ocorrência será usado. As ocorrências online de ID de transação duplicada subsequentes são processadas como se não tivessem uma ID de transação.
* Depois de preencher um determinado valor `transactionID`, o &quot;instantâneo&quot; associado é considerado imutável até que a ID da transação expire.
* Se você definir a mesma ID de transação em várias linhas de fonte de dados, todas as dimensões disponíveis da ocorrência online serão anexadas a cada ocorrência offline. Ocorrências offline para a mesma ID de transação não sabem nada umas sobre as outras; os dados não são transmitidos entre ocorrências offline.
