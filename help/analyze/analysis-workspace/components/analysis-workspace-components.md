---
description: 'Os componentes no Analysis Workspace consistem em dimensões, métricas, segmentos e intervalos de datas que você pode arrastar e soltar em um projeto. '
title: Visão geral dos componentes
uuid: 1a4e1c35-eac9-4eb4-be2e-ecb2c6728150
translation-type: tm+mt
source-git-commit: 08d61f4e41bae8a9a0a4be6a950db4ef093c4b02
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 13%

---


# Visão geral dos componentes

Os componentes no Analysis Workspace consistem em dimensões, métricas, segmentos e intervalos de datas que você pode arrastar e soltar em um projeto.

To access the Components menu, click the **Components** icon in the left rail. Você pode alternar entre [Painéis](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html), [Visualizações](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.html)e Componentes dos ícones do painel esquerdo ou usando [teclas de atalho](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md).

Você também pode ajustar as configurações [de densidade de](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html) Visualização do projeto para ver mais valores no painel esquerdo de uma só vez, indo para **Projeto > Informações e configurações do projeto > Densidade** de Visualização.

## Dimensões {#dimensions}

[**Dimension**](https://docs.adobe.com/content/help/en/analytics/components/dimensions/overview.html) são atributos de texto que descrevem o comportamento do visitante e podem ser exibidos, detalhados e comparados na análise. Eles podem ser encontrados no painel Componente esquerdo (seção laranja) e são normalmente aplicados como linhas de uma tabela.

Exemplos de dimensões incluem Nome da página, Canais de marketing, Tipo de dispositivo e Produtos. Dimension são fornecidos pelo Adobe e são capturados por meio de sua implementação personalizada (eVar, Props, classificações etc.).

Cada dimensão também contém itens **de** dimensão dentro dela. Os itens de Dimension podem ser encontrados no painel Componente esquerdo clicando na seta de divisa ao lado de qualquer nome de dimensão (os itens são amarelos).

Exemplos de itens de dimensão incluem Página inicial (na dimensão Página), Pesquisa paga (na dimensão Canal de marketing), Tablet (na dimensão Tipo de dispositivo móvel) e assim por diante.

## Métricas {#metrics}

[**As métricas**](https://docs.adobe.com/content/help/en/analytics/components/metrics/overview.html) são medidas quantitativas sobre o comportamento do visitante. Eles podem ser encontrados no painel Componente esquerdo (seção verde) e são normalmente aplicados como colunas de uma tabela.

Exemplos de métricas incluem visualizações de página, Visitas, Pedidos, Tempo médio gasto e Receita/Pedido. As métricas são fornecidas pelo Adobe, capturadas por meio de sua implementação personalizada (eventos bem-sucedidos) ou criadas usando o construtor [de métricas](https://docs.adobe.com/content/help/pt-BR/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)calculadas.

## Segmentos {#segments}

[**Segmentos**](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) são filtros de audiência aplicados à sua análise. Eles podem ser encontrados no painel Componente esquerdo (seção azul) e são normalmente aplicados na parte superior de um painel ou nas colunas de métrica acima em uma tabela.

Exemplos de segmentos incluem Visitantes de dispositivos móveis, Visitas de e-mail e Ocorrências autenticadas. Os segmentos são fornecidos pelo Adobe, criados na área de [painel](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html), ou criados usando o construtor [de segmentos](https://docs.adobe.com/content/help/pt-BR/analytics/components/segmentation/segmentation-workflow/seg-build.html).

## Intervalos de datas {#date-ranges}

[**Intervalos**](https://docs.adobe.com/content/help/pt-BR/analytics/analyze/analysis-workspace/components/calendar-date-ranges/calendar.html) de datas são o intervalo de datas nas quais você realiza a análise. Eles podem ser encontrados no painel Componente esquerdo (seção violeta) e são normalmente aplicados no calendário de cada painel.

Exemplos de intervalos de datas incluem julho de 2019, Últimas 4 semanas e Este mês. Os intervalos de datas são fornecidos por Adobe, aplicados no calendário [do](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/panels.html)painel ou criados usando o Criador [de intervalo de](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.html)datas.

## Ações dos componentes {#actions}

Você pode gerenciar componentes (individualmente ou selecionando mais de um) diretamente no painel esquerdo. Clique com o botão direito do mouse em um componente ou clique no ícone de ponto Ação na parte superior da lista do componente.

| Ação de componente | Descrição |
|--- |--- |
| Tag | Organize ou gerencie componentes aplicando tags. Você pode pesquisar por tag no painel esquerdo clicando no filtro ou digitando #. As tags também atuam como filtros nos gerenciadores de componentes. |
| Marcar como favorito | Adicione o componente à sua lista de favoritos. Como tags, você pode pesquisar por Favoritos no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
| Aprovar | Marque os componentes como Aprovado para avisar aos usuários que o componente foi aprovado pela organização. Como tags, você pode pesquisar por Aprovado no painel esquerdo e filtrar por eles nos gerenciadores de componentes. |
| Compartilhar | Compartilhe componentes para usuários em sua organização. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |
| Excluir | Exclua os componentes de que você não precisa mais. Essa opção está disponível somente para componentes personalizados, como segmentos ou métricas calculadas. |

Os componentes personalizados também podem ser gerenciados por meio de seus respectivos gerentes de componentes.
