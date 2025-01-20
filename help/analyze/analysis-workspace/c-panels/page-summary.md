---
description: O painel de resumo da página mostra as informações de resumo de uma página de sua escolha.
title: Painel Resumo da página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
source-git-commit: 76abe4e363184a9577622818fe21859d016a5cf7
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 8%

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
>abstract="Revise rapidamente algumas das métricas de alto nível, bem como o movimento de e para uma página específica.<br/><br/>**Parâmetros **<br/>**Adicionar um item de dimensão de página**: abra o painel de componentes, localize a dimensão de Página e expanda-a clicando na cenoura para ver os itens de dimensão. Em seguida, arraste e solte a página específica sobre a qual deseja aprender no construtor. Depois de arrastar e soltar o item de dimensão, o relatório será preenchido automaticamente com informações importantes sobre a página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel de resumo da página no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Não há painel equivalente em_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Esse painel permite explorar facilmente as principais estatísticas sobre páginas específicas.

## Acessar o painel

Você pode acessar o painel de [!UICONTROL Relatórios] ou de [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já está solto em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Somente a dimensão Página é compatível.</li><li>Uma configuração padrão já foi aplicada; neste caso, a página mais visitada da dimensão [!UICONTROL Página]. Você pode modificar essa configuração.</li></ul> |
| Workspace | Crie um novo projeto e selecione o ícone Painel no painel à esquerda. Arraste o painel [!UICONTROL Resumo da página] para cima da tabela de Forma livre. Observe que o campo Página [!UICONTROL Item de Dimension] está em branco. Selecione um item de dimensão na lista suspensa. |

## Entradas do painel {#Input}

Você pode configurar o painel [!UICONTROL Resumo da página] usando estas configurações de entrada:

| Configuração | Descrição |
| --- | --- |
| Zona de destino do segmento (ou outro componente) | Você pode arrastar e soltar segmentos ou outros componentes para filtrar ainda mais os resultados do painel. |
| Item de dimensão de página | Na lista suspensa, selecione o item de dimensão Página cujas estatísticas principais você deseja explorar. |

{style="table-layout:auto"}

Clique em **[!UICONTROL Criar]** para criar o painel.

## Saída do painel {#output}

O painel [!UICONTROL Resumo da página] retorna um conjunto avançado de métricas, dados e visualizações para ajudá-lo a entender melhor as estatísticas sobre páginas específicas.

| Métrica/Visualização | Descrição |
| --- | --- |
| [!UICONTROL Exibições de página] - Mês atual, até agora | Número de exibições de página para esta página no mês atual. |
| [!UICONTROL Exibições de página] - 4 semanas atrás | Número de exibições de página para esta página no último mês. |
| [!UICONTROL Exibições de página] - 52 semanas atrás | Número de exibições de página para esta página no último ano. |
| [!UICONTROL Tendência] | Um gráfico de exibição de página de tendência para este mês, 4 semanas antes e 52 semanas antes. |
| [!UICONTROL Porcentagem de todas as exibições de página] | Um número de resumo para a porcentagem de todas as exibições de página que foram para esta página. |
| [!UICONTROL Tempo gasto na página] | Um gráfico de barras horizontal listando o tempo gasto nesta página. |
| [!UICONTROL Visitas em única página] | Um número de resumo listando o número de exibições de página nas quais esta foi a única página visitada. |
| [!UICONTROL Recargas] | A métrica [!UICONTROL Recargas] mostra o número de vezes que um item de dimensão foi apresentado durante um recarregamento. A atualização do navegador por um visitante é a maneira mais comum de acionar um recarregamento. |
| [!UICONTROL Entradas] | A métrica [!UICONTROL Entradas] mostra o número de vezes que um determinado item de dimensão é capturado como o primeiro valor em uma visita. |
| [!UICONTROL Saídas] | A métrica [!UICONTROL Saídas] mostra o número de vezes que um determinado item de dimensão é registrado como o último valor em uma visita. |
| [!UICONTROL Fluxo] | Um diagrama de Fluxo com a página selecionada como ponto focal. Você pode detalhar os dados como em qualquer [Fluxograma](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

![Painel Resumo da página](assets/page-sum1.png)

![Métricas e fluxo](assets/page-sum2.png)
