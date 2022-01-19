---
description: As categorias de fonte de dados identificam os diferentes tipos de fonte de dados que oferecem uma funcionalidade semelhante.
subtopic: Data sources
title: Visão geral dos tipos de dados e categorias
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: tm+mt
source-wordcount: '903'
ht-degree: 91%

---

# Visão geral dos tipos de dados e categorias

As categorias de fonte de dados identificam os diferentes tipos de fonte de dados que oferecem uma funcionalidade semelhante.

As categorias proporcionam um meio de agrupar as fontes de dados baseado na perspectiva do usuário. Ao criar uma fonte de dados por meio da variável [!DNL Data Sources] Interface do usuário, primeiro selecione uma categoria de fonte de dados e, em seguida, um tipo de fonte de dados específico. Cada categoria contém tipos de fontes de dados que oferecem suporte a tipos semelhantes de dados. [!DNL Data Sources] O fornece as seguintes categorias de fonte de dados:

## Utilização em site {#web-usage}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Arquivos de Log do Servidor da Web] | [Log da Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | A maioria dos servidores da Web gera arquivos de log que registram todas as páginas fornecidas. Usando essa fonte de dados, você pode processar os arquivos de log a partir da maioria dos dados do servidor web e adicionar esses dados aos seus relatórios. |
| [!UICONTROL Upload em massa da Advertising Cloud] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Fornece uploads em massa manuais e automatizados pelo Excel em [!DNL Advertising Cloud]. |
| [!UICONTROL Fonte de Dados de Tráfego de Nível de Site] | [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa dados de tráfego para todo o site. Por exemplo, [!UICONTROL Exibições de página]. |
| [!UICONTROL Fonte de Dados de Tráfego Subdivididos] | [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa dados de tráfego subdivididos por outra variável de site. Por exemplo, [!UICONTROL Exibições de página] detalhado por [!UICONTROL Produto]. |

## Campanhas Publicitárias {#ad-campaigns}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Servidor de Publicidade Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing impressões e outras métricas de nível superior relacionadas a atividades de fornecimento de anúncios do servidor de anúncios. Essa é a fonte de dados do servidor de publicidade genérico e deverá ser usada se o servidor de publicidade específico não for suportado. |
| [!UICONTROL Servidor de Campanha por Email Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as métricas do servidor de campanha por email.  As métricas frequentemente incorporadas incluem o número de mensagens enviadas, as mensagens entregues e as mensagens lidas. Essa é a fonte de dados da campanha por email genérica e deverá ser usada se o servidor de campanha por email específico não for suportado. |
| [!UICONTROL Serviço Pay-Per-Click Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar dados sobre o desempenho de pagamento por clique, como impressões, cliques e custos.  Essa é a fonte de dados pay-per-click genérica e deverá ser usada se o serviço de pay-per-click específico não for suportado. |

## Gerenciamento de Relacionamento com o Cliente (CRM) {#crm}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Central de atendimento genérica] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as informações sobre a central de atendimento. As métricas mais frequentemente importadas incluem o número de chamadas, o tempo no telefone, o agente e as vendas totais.  Essa fonte de dados é a fonte de dados da central de atendimento genérica e deverá ser usada se o software da central de atendimento específico não for suportado. |
| [!UICONTROL Aplicativo de Suporte ao Cliente Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as informações do software de suporte ao cliente. Inclui métricas como o número de novos incidentes, o número de incidentes resolvidos e o tempo gasto na resolução de incidentes.  Essa é a fonte de dados de suporte ao cliente genérico e deverá ser usada se o aplicativo de serviço ao cliente específico não for suportado. |

## Satisfação do Cliente {#csat}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Dados de Pesquisa de Opinião Genéricos] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing os resultados da pesquisa de opinião de uma ferramenta de terceiros e mostrar o nível de satisfação dos clientes por meio de suas interações com o site.  Essa é a fonte de dados de pesquisa de opinião genérica e deverá ser usada se o serviço de dados da pesquisa de opinião específico não for suportado. |

## Desempenho do Site {#performance}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Velocidade de download do site genérica] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos seus dados os dados de um aplicativo ou serviço que acompanha a velocidade de seus downloads. Essa é a fonte de dados de velocidade de download genérica e deverá ser usada se o serviço ou o software de velocidade de download específico não for suportado. |

## Genérico {#generic}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Fonte de dados genérica (somente dados de resumo)] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Use essa fonte de dados quando não houver correspondência mais próxima ao tipo de dados que você deseja importar para os relatórios e análises de marketing. |
| [!UICONTROL Fonte de dados genérica (processamento completo)] | Processamento completo | O Adobe substituiu as fontes de dados de processamento completo em 31 de janeiro de 2022. [Saiba mais](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). O Adobe recomenda usar a variável [API de inserção de dados em massa (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html) em vez disso. |
| [!UICONTROL Fonte de dados genérica (ID da transação)] | <ul><li>ID da transação</li><li>ID de visitante</li></ul> | Permite vincular um evento off-line a um evento on-line. O [!UICONTROL ID da transação] atua como uma chave entre os eventos offline e online. |

## Compras on-line {#purchases}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Devoluções de produto] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar os dados de devolução do produto para associá-los à ID de compra, de modo que você possa identificar as mecanismos de busca, palavras-chave, campanhas e outros atributos com maior probabilidade de gerar devoluções. |
| [!UICONTROL Custo do produto] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite fornecer o custo real dos produtos comprados e enviados pelo seu Site, associando o custo ou o lucro a produtos individuais, de modo que você possa relatar com exatidão as campanhas, palavras-chave e promoções internas mais lucrativas para seu site. |
| [!UICONTROL Status da ordem] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite usar métricas para identificar o status de cada ordem realizada, incluindo ordens canceladas, remetidas, concluídas ou consideradas fraudulentas. O relatório de status da ordem pode identificar quais métodos de aquisição geram a maior taxa de conclusão de ordem. |

## Informações privilegiadas e cotas {#leads}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Geração de leads] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar informações sobre os resultados das vendas de cada cliente potencial geradas em seu site, incluindo a receita real gerada.  Depois que a receita for atribuída corretamente às IDs dos clientes potenciais, é possível identificar suas campanhas e promoções mais lucrativas. |
| [!UICONTROL Cota online] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar informações sobre os resultados das vendas de cada cliente potencial geradas em seu site, incluindo a receita real gerada.  Depois que a receita for atribuída corretamente às IDs dos clientes potenciais, é possível identificar suas campanhas e promoções mais lucrativas. |
| [!UICONTROL Dados da central de atendimento] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar as transações da central de atendimento, de modo que você possa identificar as táticas (campanhas, promoções etc.) que levam os clientes a pegar o telefone. |
