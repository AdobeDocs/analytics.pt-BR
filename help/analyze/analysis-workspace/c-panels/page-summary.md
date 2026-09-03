---
description: Saiba como usar o painel de resumo da página para mostrar as informações de resumo de uma página selecionada.
title: Painel Resumo da página
feature: Panels
role: User, Admin
exl-id: f0b7cd92-17b2-452d-9aab-f78629360ab8
TQID: https://experienceleague.adobe.com/WI5opV6DcvJRF--HuX8PJcJd7G-3XU0-E0hWvvdlwmM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 642
ht-degree: 87%

---

# Painel de resumo da página {#page-summary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_button"
>title="Resumo da página"
>abstract="Revise rapidamente algumas das métricas de alto nível, bem como o movimento de e para uma página específica."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_pagesummary_panel"
>title="Painel de resumo da página"
>abstract="Analise rapidamente algumas das métricas de alto nível, bem como o movimento de e para uma página específica.<br/><br/>**Parâmetros &#x200B;**<br/>**Adicionar um item de dimensão de página**: abra o painel de componentes, localize a dimensão Página e expanda-a clicando na seta para ver os itens de dimensão. Em seguida, arraste e solte a página específica sobre a qual deseja ter conhecimento no construtor. Após arrastar e soltar o item de dimensão, o relatório será preenchido automaticamente com informações importantes sobre a página."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo documenta o painel de resumo de Página no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Não há painel equivalente no_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Um painel de **[!UICONTROL resumo da página]** permite verificar as principais estatísticas sobre páginas específicas.

## Usar

Para usar um painel de **[!UICONTROL resumo da página]**:

1. Crie um painel de **[!UICONTROL resumo da página]**. Para obter informações sobre como criar um painel, consulte [Criar um painel](panels.md#create-a-panel).

1. Especifique a [entrada](#panel-input) do painel.

1. Observe a [saída](#panel-output) do painel.



É possível acessar o painel a partir de [!UICONTROL Relatórios] ou no [!UICONTROL Workspace].

| Ponto de acesso | Descrição |
| --- | --- |
| [!UICONTROL Relatórios] | <ul><li>O painel já foi solto em um projeto.</li><li>O painel esquerdo está recolhido.</li><li>Somente a dimensão Página é compatível.</li><li>Uma configuração padrão já foi aplicada, neste caso, é a página mais visitada da dimensão [!UICONTROL Página]. É possível modificar essa configuração.</li></ul> |
| Workspace | Crie um novo projeto e selecione o ícone Painel no menu à esquerda. Arraste o painel de [!UICONTROL resumo da página] sobre a tabela de forma livre. Observe que o campo [!UICONTROL Item de dimensão] da página está em branco. Selecione um item de dimensão da lista suspensa. |

### Entrada do painel {#panel-input}

É possível configurar o painel de [!UICONTROL resumo da página] usando estas configurações de entrada:

![Resumo de entrada da página](assets/page-summary-input.png)

| Entrada | Descrição |
| --- | --- |
| **[!UICONTROL Página]** | Selecione uma dimensão de página para a qual você deseja explorar as principais estatísticas. Por exemplo, **[!UICONTROL página inicial]** para explorar estatísticas da Página inicial. Use o menu suspenso para selecionar uma página ou comece a digitar (por exemplo, `home`) para procurar páginas rapidamente. |

{style="table-layout:auto"}


Selecione **[!UICONTROL Criar]** para criar o painel.

### Saída do painel {#panel-output}

O painel de [!UICONTROL resumo da página] retorna um conjunto avançado de métricas, dados e visualizações para ajudar a entender melhor as estatísticas sobre páginas específicas.

![Painel de resumo da página](assets/page-summary-output.png)

| Visualização | Descrição |
| --- | --- |
| **[!UICONTROL Exibições de página] - Mês atual (até agora)** | Uma visualização de [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições desta página no mês atual. |
| **[!UICONTROL Exibições de página] - 4 semanas antes** | Uma visualização de [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições desta página no último mês. |
| **[!UICONTROL Exibições de página] - 52 semanas antes** | Uma visualização de [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições desta página no último ano. |
| **[!UICONTROL Tendência]** | Uma visualização de tendência de [linha](/help/analyze/analysis-workspace/visualizations/line.md) para exibições de página neste mês, 4 semanas antes e 52 semanas antes. |
| **[!UICONTROL Porcentagem de todas as exibições de página]** | Um número de resumo para a porcentagem de todas as exibições referentes a esta página. |
| **[!UICONTROL Tempo gasto na página]** | Uma visualização de [barra horizontal](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) que mostra o tempo gasto nesta página. |
| **[!UICONTROL Visitas em uma única página]** | Um [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra o número de exibições de página em que esta página foi a única visitada. |
| **[!UICONTROL Recarregamentos]** | Um [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra a quantidade de vezes que um item de dimensão estava presente durante um recarregamento. A atualização do navegador por um(a) visitante é a maneira mais comum de acionar um recarregamento. |
| **[!UICONTROL Entradas]** | Um [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra a quantidade de vezes que um determinado item de dimensão foi capturado como o primeiro valor em uma visita. |
| **[!UICONTROL Saídas]** | Um [número de resumo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) que mostra a quantidade de vezes que um determinado item de dimensão foi capturado como o último valor em uma visita. |
| **[!UICONTROL Fluxo]** | Uma visualização de [fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) com a página selecionada como ponto focal. É possível aprofundar a análise dos dados da mesma forma que em qualquer visualização de [fluxo](/help/analyze/analysis-workspace/visualizations/c-flow/create-flow.md). |

{style="table-layout:auto"}

Use ![Editar](/help/assets/icons/Edit.svg) para reconfigurar e recriar o painel.
