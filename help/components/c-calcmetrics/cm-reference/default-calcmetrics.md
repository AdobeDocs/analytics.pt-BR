---
description: O Adobe fornece várias métricas calculadas que você pode usar. Esta página lista essas métricas e seus usos pretendidos.
title: 'Referência: funções básicas'
feature: Calculated Metrics
exl-id: 1a49435c-96d1-4617-bd1a-a5d3b74e3ebd
source-git-commit: 2874ea66765e650a92bc39537d6a9eb8cebcd6a4
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 10%

---

# Métricas calculadas padrão

O Adobe Analytics fornece várias Métricas calculadas para cobrir os casos de uso mais comuns. Essas Métricas calculadas estão disponíveis por padrão no Analysis Workspace.

Veja a seguir uma lista de cada Métrica calculada fornecida por Adobe, com sua função desejada e a fórmula subjacente usada para calculá-la:

>[!NOTE]
>
>Além das Métricas calculadas padrão descritas nesta página, você também pode adicionar Métricas calculadas a um conjunto de relatórios.
>
>É possível:
> * Adicione métricas calculadas padrão para mídia de streaming, conforme descrito em [Métricas calculadas](/https://experienceleague.adobe.com/docs/media-analytics/using/implementation/variables/calculated-metrics.html)
> * Crie Métricas calculadas personalizadas a partir de Métricas existentes, conforme descrito em [Métricas calculadas e calculadas avançadas (derivadas)](/help/components/c-calcmetrics/cm-overview.md).



| Nome da métrica calculada | Função | Fórmula |
|---------|----------|---------|
| Taxa de rejeição | A proporção de visitas que continham exatamente uma ocorrência em comparação ao número de visitas nessa página. Isso pode ajudá-lo a entender quais itens de dimensão têm a maior taxa de rejeição, ou ver a taxa de rejeição total do site coletada ao longo do tempo. | Taxa de rejeição |
| Receita / Visitante | A quantidade média de receita gerada por cada visitante individual do site. | <p>Receita</p><p>/</p><p>Visitantes únicos</p> |
| Pedidos/visitante | O número médio de pedidos ou transações gerados por cada visitante individual do site | <p>Pedidos padrão</p><p>/</p><p>Visitante</p> |
| Receita / visitas | A quantidade média de receita gerada por uma única visita ao site. | <p>Receita</p><p>/</p><p>Visitas únicas</p> |
| Receita / Pedido | A quantidade média de receita gerada por cada transação ou ordem concluída no site. | <p>Receita</p><p>/</p><p>Ordem</p> |
| Pedidos/visitas | A porcentagem de visitas ao site que resultam em uma transação concluída. | <p>Ordem</p><p>/</p><p>Visitas</p> |
| Exibições de página/visitas | O número médio de páginas que um usuário visualiza durante uma única visita ao site. | <p>Exibições de página</p><p>/</p><p>Visitas</p> |
| Visitas / Visitante | O número médio de visitas que um visitante único faz ao site. | <p>Visitas</p><p>/</p><p>Visitantes únicos</p> |
| Recargas / Visualizações de página | A porcentagem de exibições de página que resultaram em um recarregamento ou atualização da página. | <p>Recargas</p><p>/</p><p>Exibições de página</p> |
| Taxa de rejeição ponderada | Função | if(visitas>percentil(visitas),bouncerate,0) |
| Assistências para pedidos | O número de vezes que um canal ou fonte contribuiu para a jornada de um cliente para fazer uma compra, mas não resultou na compra final. | <p>Pedidos (Participação\|Visita)</p><p>-</p><p>Pedidos</p> |
| Taxa de saída | A porcentagem de visitantes que deixam o site após visualizar uma página específica. | <p>Saídas</p><p>/</p><p>Visitas</p> |
| Taxa de entrada | A porcentagem de visitantes que entraram no site em uma determinada página em comparação ao número total de sessões no site. | <p>Entradas</p><p>/</p><p>Visitas</p> |
| Tempo Médio no Site | O tempo médio que um visitante gasta no site antes de sair ou navegar para fora do site. | Tempo médio gasto no site (segundos) |
| Tempo gasto/usuário (estado) | O tempo que o visitante médio passa em um determinado Estado enquanto está no site | Métrica Tempo gasto por visitante (segundos) + segmento de aplicativo móvel |
| Usuários (dispositivos móveis) | O número total de usuários de um aplicativo móvel | Métrica Visitantes únicos + segmento Usuários de aplicativos móveis |
| Usuários do aplicativo | O número total de usuários de um aplicativo móvel | Métrica Visitantes únicos + segmento de aplicativo móvel |
| Exibições de estado | O número de visualizações para os diferentes estados ou telas do aplicativo | Métrica Exibições de página + segmento de aplicativo móvel |
| Ações | O número total de ações executadas no aplicativo | Métrica Instâncias de link personalizado + Tem um segmento de Ação |
| Cliques no link de aquisição | O número de vezes que as pessoas clicam em um link projetado para direcionar tráfego para o site. | Métrica de click-throughs da campanha |
| Velocidade da página | O número de exibições de página adicionais geradas por um conteúdo. Isso pode ajudá-lo a determinar qual conteúdo impulsiona o engajamento adicional. | <p>Exibições de página</p><p>/</p><p>Visitas</p> |
| Taxa de conversão | A porcentagem de visitantes que executaram a ação desejada, como fizeram uma compra. | <p>Pedidos</p><p>/</p><p>Visitas</p> |
| Duração média da sessão (dispositivos móveis) | O tempo médio que os visitantes gastam no site durante uma única sessão. | Em branco |
| Cobertura de ID de Experience Cloud | A porcentagem de visitantes que têm uma ID de Experience Cloud. | <p>Visitantes com Experience Cloud ID</p><p>/</p><p>Visitantes únicos</p> |
| Velocidade do conteúdo | A velocidade com que o novo conteúdo é criado e publicado no site e a rapidez com que ele gera o envolvimento do usuário. | <p>Exibições de página</p><p>/</p><p>Visitas</p> |
| Visitantes únicos/Visitantes únicos do ITP 2.1 | A porcentagem de visitantes únicos que usam um navegador afetado pelas limitações de cookies da ITP 2.1. Em outras palavras, clientes que não usam uma implementação CNAME. (Isso se aplica aos clientes que definem cookies por meio do JavaScript do lado do cliente.) | <p>Métrica Visitantes únicos + segmento Visitantes ITP</p><p>/</p><p>Visitantes únicos</p> |
| Visitantes únicos/Visitantes únicos que retornam após 7 dias | A porcentagem de visitantes únicos que retornam após um período de 7 dias ou mais. | <p>Métrica Visitantes únicos + Usuários que retornam após o segmento de 7 dias</p><p>/</p><p>Visitantes únicos</p> |
| Exibições de página / Visitante único | O número médio de páginas visualizadas para cada visitante único do site. | <p>Exibições de página</p><p>/</p><p>Visitantes únicos</p> |
| Visitas / Visitantes | O número médio de visitas que um visitante único faz ao site. | <p>Visitas</p><p>/</p><p>Visitantes únicos</p> |
| Visitantes únicos estimados (ITP 2.1) | <p>Para visitantes da ITP (usuários em navegadores Safari), divida Visitantes únicos por 2 ou menos.</p><p>Isso pressupõe que você esteja configurando cookies usando JavaScript do lado do cliente (não usando uma implementação CNAME). As implementações que definem cookies usando JavaScript do lado do cliente foram afetadas a partir do ITP 2.1. Consulte: [https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/)</p> | <p>Métrica Visitantes únicos + segmento Visitantes ITP (implementações ITP 2.1, não CNAME)</p><p>/</p><p>Métrica Visitantes únicos + Segmento Visitantes não ITP (ITP 2.1, implementações não CNAME)</p> |
| Exibições de página / Visitantes únicos estimados (ITP 2.1) | O número médio de páginas visualizadas para Visitantes únicos estimados (ITP 2.1). | <p>Métrica Visitantes únicos + segmento Visitantes ITP (implementações ITP 2.1, não CNAME)</p><p>/</p><p>Métrica Visitantes únicos + Segmento Visitantes não ITP (ITP 2.1, implementações não CNAME)</p> |

{style="table-layout:auto"}
