---
title: Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre
description: Como interagir com itens de dimensão dinâmicos e estáticos em tabelas.
feature: Tabelas de forma livre
role: Business Practitioner, Administrator
exl-id: 4cdc93b5-67ed-46a4-ba9f-a96e640da9d9
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: ht
source-wordcount: '484'
ht-degree: 100%

---

# Itens de dimensão dinâmicos vs estáticos em tabelas de forma livre

Nas tabelas de forma livre, as linhas e colunas podem conter vários valores de componentes. Esses valores podem ser dinâmicos (mudam com o tempo) ou estáticos (não mudam com o tempo), dependendo da análise que você deseja criar.

## Itens de dimensão dinâmicos

Os itens de dimensão dinâmicos mudam com o tempo e dependem da métrica que está sendo classificada na tabela de forma livre. Os itens de dimensão dinâmicos são usados quando você deseja analisar os itens principais de um determinado período.

Ao soltar uma dimensão em uma tabela de forma livre, linhas dinâmicas são retornadas. Elas representam os itens principais que correspondem à dimensão de uma determinada métrica e período. Também é possível soltar uma dimensão em colunas de tabela de forma livre. A dimensão se expande automaticamente para os 5 itens de dimensão principais.

Por exemplo, ao arrastar a dimensão Tipo de navegador para a tabela, os principais itens de dimensão Tipo de navegador (por exemplo, Microsoft, Apple, Google etc.) retornam dinamicamente às linhas da tabela. Se forem soltos em uma coluna, os 5 principais itens de dimensão Tipo de navegador retornarão dinamicamente.

Os itens de dimensão dinâmicos têm a opção de filtro de linha e **não** têm ícones de bloqueio e X presentes.

![](assets/dynamic-items.png)

## Itens de dimensão estáticos

Os itens de dimensão estáticos não mudam com o tempo; são componentes fixos que são sempre retornados em uma tabela de forma livre. Os itens de dimensão estáticos são usados quando você deseja sempre analisar o mesmo item, sejam campanhas específicas ou dias específicos da semana.

Sempre que você selecionar e soltar manualmente valores de componentes específicos (dimensão, métrica, segmento, intervalo de datas) em uma tabela, o resultado será uma lista estática de linhas ou colunas. Os itens de dimensão estáticos também podem ser criados se você optar por:

* Em linhas, Clique com o botão direito do mouse em > [!UICONTROL Exibir somente linhas selecionadas]
* Em colunas, Clique com o botão direito do mouse em > [!UICONTROL Tornar o item estático]

Por exemplo, ao arrastar sobre itens específicos Tipo de navegador, como Microsoft e Apple, esses 2 itens específicos sempre são puxados para a tabela.

Os itens de dimensão estáticos **não** têm a opção de filtro de linha. Em vez disso, os ícones de bloqueio e X estão presentes em cada item. Clique no ícone X para remover esse item de dimensão da tabela.

![](assets/static-items.png)

## Itens de dimensão mistos

Itens de dimensão de diferentes dimensões podem ser adicionados à mesma tabela. Nesses casos, o cabeçalho da linha indica “Dimensões mistas”. Esses itens de dimensão são estáticos. Por exemplo, adicionar itens de dimensão específicos da dimensão Tipo de navegador e outros itens de dimensão da dimensão Navegador.

![](assets/mixed-dimensions.png)

## Total de linhas de forma livre

As linhas dinâmicas e estáticas se comportam de maneira diferente na linha total de forma livre. Por padrão:

* As linhas dinâmicas são somadas no lado do servidor e deduplicam métricas como visitas ou visitantes
* As linhas estáticas são somadas no lado do cliente e **não** deduplicam as métricas. Para calcular o total de linhas do lado do servidor, altere a configuração de linha para **Mostrar total geral**. [Saiba mais](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html?lang=pt-BR)
