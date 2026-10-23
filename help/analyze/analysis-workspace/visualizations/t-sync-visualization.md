---
description: Saiba como vincular visualizações a uma fonte de dados de tabela de forma livre.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados de visualização no Analysis Workspace
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
TQID: https://experienceleague.adobe.com/ZteQfWHbl29KbcI-OUvvjEXgKytSIuR8l5R40zWQ-Rk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
subfeature_v2:
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
    internal-label: Visualizations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 19e31fec475abe3805e2637949dc86171123c210
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 18%
---
# Gerenciar fontes de dados {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear seleção"
>abstract="Habilite esta configuração para bloquear a visualização nas posições selecionadas ou nos itens selecionados na fonte de dados."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabela"
>abstract="Selecionar **[!UICONTROL Mostrar tabela]** gera uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabela"
>abstract="Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

Cada visualização no Analysis Workspace é baseada em uma fonte de dados, normalmente uma tabela de forma livre. A sincronização de visualizações permite controlar qual tabela de forma livre ou fonte de dados corresponde a uma visualização e se a visualização permanece bloqueada para linhas específicas nessa tabela.

>[!TIP]
>
>Você pode identificar quais visualizações estão relacionadas pela cor ![StatusOrange](/help/assets/icons/StatusOrange.svg) ao lado do título das visualizações. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.
>

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/23729?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

## Definir configurações da fonte de dados {#configure}

1. No Analysis Workspace, vá para a visualização cujas configurações de fonte de dados ou bloqueio você deseja configurar.

1. Passe o mouse sobre a visualização e selecione o ícone **[!UICONTROL Configurações]** ![Configuração](/help/assets/icons/Setting.svg).

1. Selecione a guia **[!UICONTROL Fonte de dados]**.

   ![Guia Fonte de dados mostrando a fonte de dados, a visualização vinculada e as configurações de seleção de bloqueio.](assets/lock-selection.png)

1. Defina qualquer uma das seguintes configurações:

   | Configuração | Descrição |
   | --- | --- |
   | **[!UICONTROL Fonte de dados]** | Selecione a fonte de dados na qual a visualização se baseia. |
   | **[!UICONTROL Visualizações vinculadas]** | Lista todas as visualizações vinculadas à fonte de dados (tabela de forma livre). |
   | **[!UICONTROL Mostrar fonte de dados]** | Mostrar ou ocultar a fonte de dados (tabela de forma livre) que corresponde à visualização. |
   | **[!UICONTROL Bloquear seleção]** | Bloqueie a visualização para as linhas atualmente selecionadas na fonte de dados e selecione **[!UICONTROL Posições selecionadas]** ou **[!UICONTROL Itens selecionados]**. Consulte [Bloquear seleção](#lock-selection). |

## Bloquear seleção {#lock-selection}

Bloquear a seleção mantém uma visualização focada nas linhas selecionadas em sua fonte de dados, mesmo quando a tabela é alterada. Por exemplo, a tabela é alterada ao classificá-la ou filtrá-la, alterar seu intervalo de datas ou aplicar um segmento. Uma visualização bloqueada mostra ![LockClosed](/help/assets/icons/LockClosed.svg) ao lado do título.

Se os segmentos, as dimensões ou as métricas na fonte de dados forem alterados e os dados bloqueados não estiverem mais visíveis, selecione **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização, separada da fonte de dados original.

Ao bloquear a seleção, escolha uma das seguintes opções:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Posições selecionadas]** | Bloqueia a visualização para as **posições** das linhas selecionadas na fonte de dados. Essas posições continuam sendo visualizadas, mesmo que os itens nelas mudem. Por exemplo, selecione essa opção para sempre mostrar os cinco principais nomes de campanha na fonte de dados, independentemente de quais campanhas eles são.<br><br>Se você bloquear linhas de detalhamento e essas linhas não estiverem mais na tabela, a visualização não será exibida. Para exibi-la novamente, atualize a tabela (por exemplo, seu intervalo de datas, segmentos ou filtros) ou atualize a seleção de bloqueio. |
| **[!UICONTROL Itens selecionados]** | Bloqueia a visualização para os **itens** específicos selecionados na fonte de dados. Esses itens continuam sendo visualizados, mesmo se a classificação na tabela mudar. Por exemplo, selecione essa opção para sempre mostrar os mesmos cinco nomes de campanha, independentemente da classificação. |
