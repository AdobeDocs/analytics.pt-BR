---
description: As categorias de fonte de dados identificam os diferentes tipos de fonte de dados que oferecem uma funcionalidade semelhante.
subtopic: Data sources
title: Visão geral dos tipos de dados e categorias
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
source-git-commit: 0b31585f5a928d68083764b80f3a08927b407387
workflow-type: ht
source-wordcount: '903'
ht-degree: 100%

---

# Visão geral dos tipos de dados e categorias

As categorias de fonte de dados identificam os diferentes tipos de fonte de dados que oferecem uma funcionalidade semelhante.

As categorias proporcionam um meio de agrupar as fontes de dados baseado na perspectiva do usuário. Ao criar uma fonte de dados por meio da interface do [!DNL Data Sources], selecione primeiro uma categoria de fonte de dados e, depois, um tipo de fonte de dados específico. Cada categoria contém tipos de fontes de dados que oferecem suporte a tipos semelhantes de dados. O [!DNL Data Sources] fornece as seguintes categorias de fonte de dados:

## Utilização em site {#web-usage}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Arquivos de log do servidor da web] | [Log da Web](/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md) | A maioria dos servidores da Web gera arquivos de log que registram todas as páginas fornecidas. Usando essa fonte de dados, você pode processar os arquivos de log a partir da maioria dos dados do servidor web e adicionar esses dados aos seus relatórios. |
| [!UICONTROL Upload em massa da Advertising Cloud] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Oferece uploads em massa manuais e automatizados pelo Excel na [!DNL Advertising Cloud]. |
| [!UICONTROL Fonte de Dados de Tráfego de Nível do Site] | [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa dados de tráfego para todo o site. Por exemplo, [!UICONTROL Visualizações de Página]. |
| [!UICONTROL Fonte de Dados de Tráfego Detalhados] | [Tráfego](/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md) | Importa dados de tráfego detalhados por outra variável do site. Por exemplo, [!UICONTROL Visualizações de página] detalhadas por [!UICONTROL Produto]. |

## Campanhas Publicitárias {#ad-campaigns}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Servidor de Publicidade Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing impressões e outras métricas de nível superior relacionadas a atividades de fornecimento de anúncios do servidor de anúncios. Essa é a fonte de dados do servidor de publicidade genérico e deverá ser usada se o servidor de publicidade específico não for suportado. |
| [!UICONTROL Servidor de Campanha de E-mail Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as métricas do servidor de campanha por e-mail.  As métricas frequentemente incorporadas incluem o número de mensagens enviadas, as mensagens entregues e as mensagens lidas. Essa é a fonte de dados da campanha por email genérica e deverá ser usada se o servidor de campanha por email específico não for suportado. |
| [!UICONTROL Serviço Pay-Per-Click Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar dados sobre o desempenho de pagamento por clique, como impressões, cliques e custos.  Essa é a fonte de dados pay-per-click genérica e deverá ser usada se o serviço de pay-per-click específico não for suportado. |

## Gerenciamento de Relacionamento com o Cliente (CRM) {#crm}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Central de atendimento genérica] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as informações sobre a central de atendimento. As métricas mais frequentemente importadas incluem o número de chamadas, o tempo no telefone, o agente e as vendas totais.  Esta fonte de dados é a fonte de dados da central de atendimento genérica e deverá ser usada se o software da central de atendimento específico não for suportado. |
| [!UICONTROL Aplicativo de Suporte ao Cliente Genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing as informações do software de suporte ao cliente. Inclui métricas como o número de novos incidentes, o número de incidentes resolvidos e o tempo gasto na resolução de incidentes.  Essa é a fonte de dados de suporte ao cliente genérico e deverá ser usada se o aplicativo de serviço ao cliente específico não for suportado. |

## Satisfação do Cliente {#csat}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Dados de Pesquisa de Opinião Genéricos] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar aos relatórios de marketing os resultados da pesquisa de opinião de uma ferramenta de terceiros e mostrar o nível de satisfação dos clientes por meio de suas interações com o site.  Essa é a fonte de dados de pesquisa de opinião genérica e deverá ser usada se o serviço de dados da pesquisa de opinião específico não for suportado. |

## Desempenho do Site {#performance}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Velocidade de download do site genérico] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite integrar dados de um aplicativo ou serviço que rastreia a velocidade de seus downloads com seus dados. Essa é a fonte de dados de velocidade de download genérica e deverá ser usada se o serviço ou o software de velocidade de download específico não for suportado. |

## Genérico {#generic}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Fonte de dados genérica (somente dados de resumo)] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Use esta fonte de dados quando não houver correspondência mais próxima ao tipo de dados que você deseja importar para os relatórios e análises de marketing. |
| [!UICONTROL Fonte de dados genérica (processamento completo)] | Processamento completo | A Adobe descontinuou as fontes de dados de processamento completo em 31 de janeiro de 2022. [Saiba mais](/help/import/c-data-sources/c-datasrc-types/datasrc-fullproc-eol.md). Em vez disso, a Adobe recomenda o uso da [API de inserção de dados em massa (BDIA)](https://www.adobe.io/apis/experiencecloud/analytics/docs.html?lang=pt-BR). |
| [!UICONTROL Fonte de dados genérica (ID da transação)] | <ul><li>ID da transação</li><li>ID de visitante</li></ul> | Permite vincular um evento off-line a um evento on-line. A [!UICONTROL ID de transação] atua como uma chave entre os eventos off-line e on-line. |

## Compras on-line {#purchases}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Devoluções de produto] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite importar os dados de devolução do produto para associá-los à ID de compra, de modo que você possa identificar mecanismos de busca, palavras-chave, campanhas e outros atributos com maior probabilidade de gerar devoluções. |
| [!UICONTROL Custo do produto] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite fornecer o custo real dos produtos comprados e enviados pelo seu site, associando o custo ou o lucro com produtos individuais, de modo que você possa relatar com exatidão as campanhas, palavras-chave e promoções internas mais lucrativas para o seu site. |
| [!UICONTROL Status do pedido] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite usar métricas para identificar o status de cada pedido realizado, incluindo pedidos cancelados, remetidos, concluídos ou considerados fraudulentos. O relatório de status da ordem pode identificar quais métodos de aquisição geram a maior taxa de conclusão de ordem. |

## Informações privilegiadas e cotas {#leads}

| Fonte de dados | Tipo de processamento | Descrição |
| --- | --- | --- |
| [!UICONTROL Geração de clientes potenciais] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar informações sobre os resultados de cada cliente potencial gerado em seu site, incluindo a receita real gerada.  Depois que a receita é atribuída corretamente às IDs dos clientes potenciais, é possível identificar suas campanhas e promoções mais lucrativas. |
| [!UICONTROL Cotação online] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar informações sobre os resultados de cada cliente potencial gerado em seu site, incluindo a receita real gerada.  Depois que a receita é atribuída corretamente às IDs dos clientes potenciais, é possível identificar suas campanhas e promoções mais lucrativas. |
| [!UICONTROL Dados da central de atendimento] | [Conversão](/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md) | Permite carregar as transações da central de atendimento, de modo que você possa identificar as táticas (campanhas, promoções etc.) que levam os clientes a pegar o telefone. |
