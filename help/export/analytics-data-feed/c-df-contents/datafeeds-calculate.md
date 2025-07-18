---
description: Descreve como calcular métricas comuns usando feeds de dados.
keywords: Feed de dados;tarefa;métrica;coluna pré;coluna pós;bots;filtragem de data;sequência de eventos;comum;fórmulas
title: Calcular métricas
feature: Data Feeds
exl-id: f9b0d637-7a6e-416a-adff-3c7e533bfac7
source-git-commit: adee2f1013cfd2ae231e3133b5a5327b8792bd16
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 76%

---

# Usar feeds de dados para calcular métricas comuns

Descreve como calcular métricas comuns usando feeds de dados.

>[!NOTE]
>
>As ocorrências normalmente excluídas do Analysis Workspace são incluídas nos feeds de dados. Considere adicionar as seguintes condições às suas consultas se elas forem relevantes:
>
>* **`exclude_hit`**: o Analysis Workspace inclui apenas dados em que `exclude_hit = 0`.
>* **`customer_perspective`**: o Analysis Workspace inclui apenas dados em que `customer_perspective = 0`, a menos que você use um conjunto de relatórios virtual que inclua ocorrências em segundo plano móveis.
>* **`hit_source`**: dados de fontes de dados podem conter diferenças entre dados brutos e o Analysis Workspace. Se quiser excluir ocorrências de fontes de dados, exclua todas as linhas nas quais `hit_source = 5,7,8,9`.

## Exibições de página

1. Conte o número de linhas nas quais um valor está em `post_pagename` ou `post_page_url`.

## Ocorrências

1. Conte o número total de linhas.

## Visitas

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num`e `visit_start_time_gmt`.
1. Conte o número exclusivo de valores.

>[!TIP]
>
>Irregularidades na Internet, irregularidades no sistema ou o uso de IDs de visitante personalizados raramente podem usar os mesmos valores `visit_num` para diferentes visitas. Embora seja opcional, use `visit_start_time_gmt` ao contar visitas para garantir que essas visitas sejam contadas.

## Visitantes

Todos os métodos que a Adobe usa para identificar visitantes únicos (ID de visitante personalizada, serviço da Experience Cloud ID etc.) são calculados como um valor em `post_visid_high` e `post_visid_low`. A concatenação dessas duas colunas pode ser usada como padrão para identificar visitantes únicos, independentemente de como eles foram identificados como um visitante único. Se você quiser entender qual método a Adobe usou para identificar um visitante único, use a coluna `post_visid_type`.

1. Concatenar `post_visid_high` e `post_visid_low`.
2. Conte o número exclusivo de valores.

## Links personalizados, de download ou de saída

1. Contar o número de linhas onde:
   * `post_page_event = 100` para links personalizados
   * `post_page_event = 101` para links de download
   * `post_page_event = 102` para links de saída

## Eventos personalizados

Todas as métricas são contadas na `post_event_list` coluna como números inteiros delimitados por vírgulas. Use `event.tsv` para corresponder valores numéricos ao evento desejado. Por exemplo, `post_event_list = 1,200` indica que a ocorrência continha um evento de compra e um evento personalizado 1.

1. Conte o número de vezes em que o valor de pesquisa do evento aparece em `post_event_list`.

## Tempo gasto

As ocorrências devem primeiro ser agrupadas por visita e, em seguida, ordenadas de acordo com o número da ocorrência na visita.

1. Concatenar `post_visid_high`, `post_visid_low`, `visit_num`e `visit_start_time_gmt`.
2. Classifique por esse valor concatenado e aplique uma classificação secundária por `visit_page_num`.
3. Se uma ocorrência não for a última em uma visita, subtraia o `post_cust_hit_time` valor do `post_cust_hit_time` valor da ocorrência subsequente.
4. Esse número é a quantidade de tempo gasto (em segundos) para a ocorrência. Os filtros podem ser aplicados para manter o foco nos itens de dimensão ou eventos.

## Pedidos, unidades e receita

Se o `currency` valor de uma ocorrência não corresponder à moeda de um conjunto de relatórios, ele será convertido usando a taxa de conversão desse dia. A coluna `post_product_list` usa o valor da moeda convertida, de modo que todas as ocorrências usam a mesma moeda nesta coluna.

1. Excluir todas as linhas nas quais `duplicate_purchase = 1`.
2. Incluir somente linhas nas quais `event_list` contém o evento compra.
3. Analise a coluna `post_product_list` para extrair todos os dados de preço. A coluna `post_product_list` é formatada da mesma forma que a `s.products` variável.
4. Calcule a métrica desejada:
   * Contar o número de linhas para calcular Pedidos
   * Soma o número de unidades na sequência de produtos `quantity` para calcular Unidades
   * Soma o número de `price` na string do produto para calcular a receita
