---
description: Saiba como sincronizar uma tabela de forma livre ou uma fonte de dados para a visualização correspondente.
keywords: Analysis Workspace;Sincronizar visualização com a fonte de dados
title: Gerenciar fontes de dados
feature: Visualizations
role: User, Admin
exl-id: 0500b27a-032e-4dc8-98b7-58519ef59368
source-git-commit: f258a1150a4bee11f5922d058930dc38b1ddfa14
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 89%

---

# Gerenciar fontes de dados {#manage-data-sources}

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection"
>title="Bloquear seleção"
>abstract="Habilite esta configuração para bloquear a visualização nas posições selecionadas ou nos itens selecionados na fonte de dados."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_lockselection_showtable"
>title="Mostrar tabela"
>abstract="Selecionar **[!UICONTROL Mostrar tabela]** gerará uma nova fonte de dados para a visualização atual, separada da fonte de dados original."

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_showtable"
>title="Mostrar tabela"
>abstract="Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original."


A sincronização de visualizações permite controlar qual tabela de forma livre ou fonte de dados corresponde a uma visualização.


>[!TIP]
>
>Você pode identificar quais visualizações estão relacionadas pela cor ![StatusOrange](/help/assets/icons/StatusOrange.svg) ao lado do título das visualizações. Cores iguais significam que as visualizações têm como base a mesma fonte de dados.
>

Você pode mostrar ou ocultar a fonte de dados. Você também pode bloquear a seleção para posições ou itens selecionados. Essas configurações determinam a maneira como a visualização muda (ou não muda) quando chegam novos dados.

![A caixa de diálogo de opções Fonte de dados mostrando as opções descritas na próxima seção.](assets/lock-selection.png)

<!--
**Tip:** You can tell which visualizations are related by the color of the dot next to the title. Matching colors mean that visualizations are based on the same data source.

Managing a data source lets you show the data source or lock the selection. These settings determine how the visualization changes (or doesn't change) when new data comes in.

1. [Create a project](/help/analyze/analysis-workspace/home.md) with a data table and a [visualization](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md).
1. In the data table, select the cells (data source) you want to associate with the visualization.
1. In the visualization, click the dot next to the title to bring up the **[!UICONTROL Data Source]** dialog. Select **[!UICONTROL Show Data Source]** or **[!UICONTROL Lock Selection]**.

   ![](assets/manage-data-source.png)

   Synchronizing a visualization to a table cell creates a new (hidden) table and color-codes the synchronized visualization with that table.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data source settings](https://video.tv.adobe.com/v/30853?quality=12&learn=on&captions=por_br){target="_blank"} for a demo video.

>[!ENDSHADEBOX]

-->

| Opção | Descrição |
|--- |--- |
| **[!UICONTROL Fonte de dados]** | Selecione a fonte de dados em que a visualização se baseia no menu suspenso. |
| **[!UICONTROL Visualizações vinculadas]** | Lista todas as visualizações vinculadas. Aplica-se à fonte de dados (tabela de forma livre). |
| **[!UICONTROL Mostrar fonte de dados]** | Permite mostrar ou ocultar a fonte de dados (tabela de forma livre) que corresponde à visualização. |
| **[!UICONTROL Bloquear seleção]** | Selecione esta opção para bloquear a visualização ![LockClosed](/help/assets/icons/LockClosed.svg) dos dados atualmente selecionados na tabela de dados correspondente. Uma vez habilitada, escolhe entre:  <ul><li>**Posições selecionadas**: a visualização está bloqueada nas **posições** selecionadas na tabela de dados correspondente. Essas posições continuarão a ser visualizadas, mesmo se os itens específicos nessas posições forem alterados (por exemplo, devido a classificação ou filtragem). Por exemplo, selecione esta opção se quiser mostrar os cinco principais nomes de campanha listados na fonte de dados nesta visualização o tempo todo. Não importa quais nomes de campanha apareçam.</li> <li>**Itens selecionados**: a visualização está bloqueada nos **itens** específicos atualmente selecionados na tabela de dados correspondente. Esses itens continuarão a ser visualizados, mesmo que as suas classificações sejam alteradas na tabela. Por exemplo, selecione esta opção se quiser mostrar os mesmos cinco nomes de campanha específicos listados na fonte de dados nesta visualização o tempo todo. Não importa a classificação desses nomes de campanha.</li></ul>Se a visualização estiver bloqueada para dados que não estão mais visíveis na tabela de dados conectada, você poderá gerar uma nova tabela. Selecione a opção **[!UICONTROL Mostrar tabela]** para gerar uma nova fonte de dados para a visualização atual, separada da fonte de dados original. |
