---
description: O painel de resumo da página mostra as informações de resumo de uma página de sua escolha.
title: Painel Resumo da página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 2aaa8c0d13755b40ec701ca6342ab773103a0422
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 25%

---

# Painel Resumo da página {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Resumo da página"
>abstract="Revise rapidamente algumas das métricas de alto nível, bem como o movimento de e para uma página específica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Painel Resumo da página"
>abstract="Revise rapidamente algumas das métricas de alto nível, bem como o movimento de e para uma página específica.<br/><br/>**Parâmetros **<br/>**Adicionar um item da dimensão página**: abra o painel de componentes, localize a dimensão Página e expanda-a clicando na cenoura para ver os itens de dimensão. Em seguida, arraste e solte a página específica sobre a qual deseja ter conhecimento no construtor. Depois de arrastar e soltar o item de dimensão, o relatório é preenchido automaticamente com informações importantes sobre a página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel de resumo da página no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Não há painel equivalente em_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Um painel **[!UICONTROL Resumo da página]** permite explorar as principais estatísticas sobre páginas específicas.

## Usar

Para usar um painel **[!UICONTROL Resumo da página]**:

1. Crie um painel **[!UICONTROL Resumo da página]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.



Você pode acessar o painel de [!UICONTROL Relatórios] ou de [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já está solto em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Somente a dimensão Página é compatível.</li><li>Uma configuração padrão já foi aplicada; neste caso, a página mais visitada da dimensão [!UICONTROL Página]. Você pode modificar essa configuração.</li></ul> |
| Workspace | Crie um novo projeto e selecione o ícone Painel no painel à esquerda. Arraste o painel [!UICONTROL Resumo da página] para cima da tabela de Forma livre. Observe que o campo Página [!UICONTROL Item de Dimension] está em branco. Selecione um item de dimensão na lista suspensa. |

### Entrada do painel {#panel-input}

Você pode configurar o painel [!UICONTROL Resumo da página] usando estas configurações de entrada:

![Resumo de entrada da página](assets/page-summary-input.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Página]** | Selecione uma dimensão de página para a qual você deseja explorar as principais estatísticas. |

{style="table-layout:auto"}


Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel {#panel-output}

O painel [!UICONTROL Resumo da página] retorna um conjunto avançado de métricas, dados e visualizações para ajudá-lo a entender melhor as estatísticas sobre páginas específicas.

![Painel Resumo da página](assets/page-summary-output.png)

| Visualização | Descrição |
| --- | --- |
| **[!UICONTROL Exibições de página] - Mês atual (até agora)** | Uma visualização de [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições de página para esta página no mês atual. |
| **[!UICONTROL Exibições de página] - 4 semanas antes** | Uma visualização de [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições de página para esta página no último mês. |
| **[!UICONTROL Exibições de página] - 52 semanas antes** | Uma visualização de [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições de página para esta página no último ano. |
| **[!UICONTROL Tendência]** | Uma visualização de tendência de [Linha](/help/analyze/analysis-workspace/visualizations/line.md) para exibições de página para este mês, 4 semanas antes e 52 semanas antes. |
| **[!UICONTROL Porcentagem de todas as exibições de página]** | Um número de resumo para a porcentagem de todas as exibições de página que foram para esta página. |
| **[!UICONTROL Tempo gasto na página]** | Uma visualização de [Barra horizontal](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) que mostra o tempo gasto nesta página. |
| **[!UICONTROL Visitas em única página]** | Um [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições de página em que esta página foi a única página visitada. |
| **[!UICONTROL Recargas]** | Um [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento. |
| **[!UICONTROL Entradas]** | Um [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de vezes que um determinado item de dimensão é capturado como o primeiro valor em uma visita. |
| **[!UICONTROL Saídas]** | Um [Número do resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de vezes que um determinado item de dimensão é capturado como o último valor em uma visita. |
| **[!UICONTROL Fluxo]** | Uma visualização de [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) com a página selecionada como ponto focal. Você pode detalhar os dados da mesma forma que em qualquer visualização de [Fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar e recriar o painel.
