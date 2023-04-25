---
description: O Adobe fornece várias métricas calculadas que podem ser usadas. Esta página lista essas métricas e suas utilizações desejadas.
title: Métricas calculadas padrão
feature: Calculated Metrics
exl-id: 84468e63-f967-41cd-8084-525b1b90957a
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '735'
ht-degree: 51%

---

# Métricas calculadas padrão

O Adobe Analytics fornece várias métricas calculadas para abranger os casos de uso mais comuns. Essas métricas calculadas estão disponíveis por padrão no Analysis Workspace.

Veja a seguir uma lista de cada métrica calculada fornecida pelo Adobe, com sua função pretendida e a fórmula subjacente usada para calculá-la:

>[!NOTE]
>
>Além das métricas calculadas padrão descritas nesta página, também é possível adicionar métricas calculadas adicionais a um conjunto de relatórios.
>
>É possível:
> * Adicione métricas calculadas padrão para mídia de transmissão, conforme descrito em [Métricas calculadas](https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Crie métricas calculadas personalizadas a partir de métricas existentes, conforme descrito em [Métricas calculadas e calculadas avançadas (derivadas)](/help/components/c-calcmetrics/cm-overview.md).



| Nome da métrica calculada | Função | Fórmula |
| --- | --- | --- |
| Cliques no link de aquisição | O número de vezes que as pessoas clicam em um link criado para direcionar tráfego para o site. | `[Campaign Click-throughs]` |
| Ações | O número total de ações executadas no aplicativo | `[Has an Action] (segment)`<br>`[Custom Link Instances] (metric)` |
| Usuários do aplicativo | O número total de usuários de um aplicativo para dispositivos móveis | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Duração média da sessão (móvel) | O tempo médio que os visitantes gastaram no site durante uma única sessão. | Em branco |
| Tempo Médio no Site | O tempo médio que um visitante gasta no site antes de sair ou sair. | `[Average Time Spent on Site (Seconds)]` |
| Taxa de rejeição | A proporção de visitas que continha exatamente uma ocorrência em comparação ao número de visitas nessa página. Essa métrica pode ajudar você a entender quais itens de dimensão têm a maior taxa de rejeição, ou para ver a taxa de rejeição total do site coletada ao longo do tempo. | `[Bounces] / [Entries]` |
| Taxa de exibições da página de bot | A proporção de exibições da página de bot em comparação ao número total de exibições da página. | `[Bot Page Views] / [Page Views]` |
| Velocidade do conteúdo | A velocidade com que um novo conteúdo é criado e publicado no site e a rapidez com a qual ele gera o engajamento do usuário. | `[Page Views] / [Visits]` |
| Taxa de conversão | A porcentagem de visitantes que executaram uma ação desejada, como fazer uma compra. | `[Orders] / [Visits]` |
| Taxa de entrada | A porcentagem de visitantes que entraram no site em uma determinada página, em comparação ao número total de sessões no site. | `[Entries] / [Visits]` |
| Visitantes únicos estimados (ITP 2.1) | Para visitantes ITP (usuários em navegadores Safari), divida Visitantes únicos por 2 ou menos. Essa métrica calculada assume que você está definindo cookies usando JavaScript do lado do cliente (não usando uma implementação CNAME). As implementações que definem cookies usando JavaScript do lado do cliente foram afetadas a partir da ITP 2.1. Consulte [Prevenção de rastreamento inteligente](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) para obter detalhes. | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors metric + Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Cobertura da Experience Cloud ID | A porcentagem de visitantes com uma ID da Experience Cloud. | `[Visitors with Experience Cloud ID] / [Unique Visitors]` |
| Taxa de saída | A porcentagem de visitantes que saem do site após visualizar uma página específica. | `[Exits] / [Visits]` |
| Visitantes únicos da ITP 2.1/Visitantes únicos | A porcentagem de visitantes únicos que usam um navegador afetado pelas limitações de cookies da ITP 2.1. | `[Unique Visitors metric with ITP Visitors segment] / [Unique Visitors]` |
| Assistências de pedidos | O número de vezes que um canal ou fonte contribuiu para a jornada de um cliente até a compra, mas não resultou na compra final. | `[Orders (Visit Participation)] - [Orders]` |
| Pedidos/visitas | A porcentagem de visitas ao site que resultam em uma transação concluída. | `[Orders] / [Visits]` |
| Pedidos/visitante | O número médio de pedidos ou transações gerados por cada visitante individual do site | `[Orders] / [Unique Visitors]` |
| Exibições de página/Número estimado de visitantes únicos (ITP 2.1) | O número médio de páginas visualizadas por visitantes únicos estimados (ITP 2.1). | `[Unique Visitors (metric) with ITP Visitors (ITP 2.1, Non-CNAME implementations) segment] / [Unique Visitors (metric) with Non-ITP Visitors (ITP 2.1, Non-CNAME implementations) segment]` |
| Exibições de página/Visitante único | O número médio de páginas visualizadas por cada visitante único do site. | `[Page Views] / [Unique Visitors]` |
| Exibições de página/visitas | O número médio de páginas que um usuário visualiza durante uma única visita ao site. | `[Page Views] / [Visits]` |
| Velocidade da página | O número de exibições de página adicionais geradas por um conteúdo. Essa métrica pode ajudar você a determinar qual conteúdo gera envolvimento adicional. | `[Page Views] / [Visits]` |
| Recargas / Visualizações de página | O percentual de visualizações de página que resultaram em um recarregamento ou atualização da página. | `[Reloads] / [Page Views]` |
| Receita/pedido | A receita média gerada por cada transação ou pedido concluído no site. | `[Revenue] / [Orders]` |
| Receita/visitas | A receita média gerada por uma única visita ao site. | `[Revenue] / [Visits]` |
| Receita/visitante | A receita média gerada por cada visitante individual do site. | `[Revenue] / [Unique Visitors]` |
| Exibições de estado | O número de visualizações dos diferentes estados ou telas do aplicativo | `[Mobile App Users] (segment)`<br>`[Page Views] (metric)` |
| Tempo Gasto/Usuário (Estado) | O tempo que o visitante médio passa em um estado específico enquanto está no site | `[Mobile App Users] (segment)`<br>`[Time Spent per Visitor (Seconds)] (metric)` |
| Visitantes únicos / Visitantes únicos que retornam após 7 dias | A porcentagem de visitantes únicos que retornam após um período de 7 ou mais dias. | `[Unique Visitors metric with Users returning after 7 days segment] / [Unique Visitors]` |
| Usuários (Dispositivo móvel) | O número total de usuários de um aplicativo para dispositivos móveis | `[Mobile App Users] (segment)`<br>`[Unique Visitors] (metric)` |
| Visitas / Visitante | O número médio de visitas que um visitante único faz ao site. | `[Visits] / [Unique Visitors]` |
| Taxa de rejeição ponderada | Função | `IF([Visits] > PERCENTILE([Visits]), [Bounce Rate], 0)` |

{style="table-layout:auto"}
