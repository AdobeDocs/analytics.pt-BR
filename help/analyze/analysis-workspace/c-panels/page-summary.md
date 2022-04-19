---
description: O painel de resumo da página mostra as informações de resumo de uma página de sua escolha.
title: Painel de resumo da página
feature: Panels
role: User, Admin
source-git-commit: 4bb950350d258b8d608f6d95d37d7d860e23ed2c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 9%

---


# Painel de resumo da página

O [!UICONTROL Resumo da página] painel iniciado como um relatório no Reports &amp; Analytics, em Relatórios > Envolvimento > Análise da página > Resumo da página. Agora também é um painel do Workspace. Este painel permite que você explore facilmente as principais estatísticas sobre páginas específicas.

## Acessar o painel

Você pode acessar o painel por meio de [!UICONTROL Relatórios] ou [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já está em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Somente a dimensão Página é compatível.</li><li>Uma configuração padrão já foi aplicada. Nesse caso, a página principal visitada para a variável[!UICONTROL Página] dimensão. Você pode modificar essa configuração.</li></ul> |
| Workspace | Crie um novo projeto e selecione o ícone Painel no painel à esquerda. Arraste o [!UICONTROL Resumo da página] acima da tabela de Forma livre. Observe que a página [!UICONTROL Dimension Item] é deixado em branco. Selecione um item de dimensão na lista suspensa. |

## Entradas do painel {#Input}

Você pode configurar o [!UICONTROL Item seguinte ou anterior] painel usando estas configurações de entrada:

| Configuração | Descrição |
| --- | --- |
| Zona Segmento (ou outro componente) | Você pode arrastar e soltar segmentos ou outros componentes para filtrar ainda mais os resultados do painel. |
| Item de dimensão da página | Na lista suspensa, selecione o item de dimensão cujas estatísticas principais deseja explorar. |

{style=&quot;table-layout:auto&quot;}

Clique em **[!UICONTROL Criar]** para criar o painel.

## Saída do painel {#output}

O [!UICONTROL Resumo da página] O painel retorna um conjunto avançado de métricas de dados e visualizações para ajudá-lo a entender melhor as estatísticas sobre páginas específicas.

| Métrica/Visualização | Descrição |
| --- | --- |
| [!UICONTROL Exibições de página] - Mês atual, até agora | Número de exibições de página para esta página no mês atual. |
| [!UICONTROL Exibições de página] - 4 semanas antes | Número de exibições de página para essa página no último mês. |
| [!UICONTROL Exibições de página] - 52 semanas antes | Número de exibições de página para essa página no último ano. |
| [!UICONTROL Tendência] | Um gráfico de exibição de página com tendência para este mês, 4 semanas antes e 52 semanas antes. |
| [!UICONTROL Porcentagem de todas as exibições da página] | Um número de resumo para a porcentagem de todas as exibições de página que foram para esta página. |
| [!UICONTROL Tempo gasto na página] | Um gráfico de barras horizontal que lista o tempo gasto nesta página. |
| [!UICONTROL Visitas em única página] | Um número de resumo que lista o número de exibições da página, onde esta foi a única página visitada. |
| [!UICONTROL Recargas] | O [!UICONTROL Recargas] mostra o número de vezes que um item de dimensão esteve presente durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento. |
| [!UICONTROL Entradas] | O [!UICONTROL Entradas] mostra o número de vezes que um determinado item de dimensão é capturado como o primeiro em uma visita. |
| [!UICONTROL Saídas] | O [!UICONTROL Saídas] mostra o número de vezes que um determinado item de dimensão é capturado como o último valor em uma visita. |
| [!UICONTROL Fluxo] | Um diagrama de Fluxo com a página selecionada como ponto focal. Você pode detalhar os dados da mesma forma que em qualquer [Diagrama de fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/creating-flow-report.md). |

{style=&quot;table-layout:auto&quot;}
