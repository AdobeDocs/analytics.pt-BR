---
description: Como usar métricas nos relatórios de Canal de marketing.
subtopic: Marketing channels
title: Métricas usadas nos relatórios de canal de marketing
topic: Reports and analytics
uuid: be5bcb94-927e-4b5f-b201-3d54eb51e740
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Métricas usadas nos relatórios de canal de marketing

Como usar métricas nos relatórios de Canal de marketing.

![](assets/metric_edit_icon.png)

Adicione (ou edite) as métricas.

![](assets/add_column_icon.png)

Adicionar uma coluna ao relatório.

## Métricas de primeiro e último contato {#first-and-last-touch}

Primeiro toque e último toque são atributos de canal que permitem ver quantos novos envolvimentos (ou dados de métrica como visualizações de produto, receita e pedidos) resultam de uma atividade do visitante no canal.

Quando um evento de sucesso ocorre, o Analytics observa toda a atividade e histórico do visitante (de volta à [expiração do envolvimento do visitante](/help/components/c-marketing-channels/visitor-engagement.md)). Nota o primeiro canal pelo qual o usuário chegou, bem como o canal mais recente. Em seguida, dá o crédito do evento de sucesso a cada canal apropriado.

<!-- 

<note>
  A first-touch value has a rolling expiration based on the frequency of a visitor returning to the site. This first-touch expiration resets whenever a visitor returns to the site. This effects reporting by causing first-touch values to persist longer than you might expect. For example, this can occur if an instance of an first-touch channel was created a year ago. Remove the values on the eVar in the admin console to reset.
</note>

 -->

**Exemplo**

Suponha que você tenha configurado até dois canais de marketing: Pesquisa paga e Campanha de email.

![](assets/paid_search.png)

Pesquisa paga é um anúncio de um produto. Ele captura o interesse do visitante e gera uma visualização do produto, mas não resulta em um evento de conversão.

![](assets/email_campaign.png)

Um mês depois, você faz uma campanha por email para o mesmo produto. Ela resulta em uma compra de US$ 100,00 (ou outro evento de conversão desejado).

No Relatório de canal de marketing, o resultado pode ser exibido como segue:

![](assets/report-graphic.png)

O Canal de pesquisa paga recebe US$ 100,00 de crédito como canal de primeiro toque para receita, com 1 ordem de primeiro toque. O canal de Campanha por email recebe US$ 100,00 de crédito como canal de receita de último toque (o canal com que o usuário teve toque pela última vez antes do evento de conversão), e com 1 ordem de último toque. Em outras palavras, a finalidade principal do relatório é visualizar como a análise de receita entre canais de primeiro toque difere da análise de receita entre canais de último toque.

Toda instância de evento de sucesso terá exatamente um canal de Primeiro toque e exatamente um canal de Último toque. Isso significa que se você adicionar uma determinada coluna de métrica em algum evento de sucesso, ela sempre será exatamente igual ao total no mesmo período de tempo. Esse total também será exatamente igual ao número total de eventos no relatório adequado de [!UICONTROL Métricas do site] &gt; [!UICONTROL Eventos personalizados]. As métricas de evento de não sucesso, como visitas e visitantes, não corresponderão 1 a 1, visto que vários canais podem ser acionados na mesma visita.

> [!NOTE] Esse relatório utiliza a versão de primeiro e último toque de cada métrica. Portanto, os dados exibidos em um relatório de [!UICONTROL Canal de marketing] podem não corresponder aos dados exibidos em outros relatórios.

## Definições de métricas {#metric-defs}

| Métrica | Definição |
|--- |--- |
| Canal de primeiro toque | O primeiro canal de marketing que interagiu com um visitante. Tecnicamente, o canal de primeiro toque é uma eVar com alocação original. |
| Visitante de primeiro toque | No relatório do canal, um visitante de primeiro toque é um Visitante único diário, originário de um canal. O envolvimento do visitante é armazenado pela duração do período de envolvimento com o site, que pode se estender por diversas visitas. |
| Canal de último toque | O canal de conversão, ou seja, o último canal de marketing que interagiu com o visitante e resultou em uma conversão. Apenas um canal é definido como canal de primeiro toque. O canal de último toque pode mudar com cada visita de retorno ao site. Cada visita tem um canal de primeiro e último toque, mas o valor do canal de primeiro toque nunca muda com visitas subsequentes. |

## Click-through {#click-through}

Um click-through é uma instância do canal de último toque. É uma eVar com a alocação mais recente.

Por exemplo, suponha que um usuário visite o seu site da Web uma vez por dia, e que cada visita tenha origem em um diferente canal de marketing:

* Dia 1: Pesquisa paga
* Dia 2: Exibição
* Dia 3: Pesquisa natural
* Dia 4: Exibição
* Dia 5: Pesquisa paga
* Dia 6: Exibição
* Dia 7: Pesquisa natural

O relatório de Canal de primeiro toque deve exibir um novo envolvimento para uma Pesquisa paga. Todos os outros canais devem exibir 0 novos envolvimentos. O relatório de Canal de último toque deve exibir 2 click-throughs para Pesquisas pagas, 3 para Exibição e 2 para Pesquisa natural.

## Adicionar métricas a um relatório de Canal de marketing {#add-metrics-to-mktg-channel-rpt}

Adicione métricas um relatório de Canal de marketing. É possível adicionar até quatro métricas a cada coluna do relatório, e quantas colunas você quiser.

1. Abra o [!UICONTROL Relatório de canal de marketing].
1. Clique em Adicionar Métricas.

   ![](assets/metric_edit_icon.png)

1. Em [!UICONTROL Métricas disponíveis], arraste e solte as métricas da seção [!UICONTROL Métricas disponíveis] para a seção [!UICONTROL Métricas selecionadas].

   ![Resultado da etapa](assets/metric_create.png)

1. Para criar métricas calculadas, procure por [!UICONTROL Métricas calculadas]**e clique em[!UICONTROL Criar]**.
1. Clique em **[!UICONTROL Salvar.]**
