---
title: Tabela de forma livre
description: As tabelas de forma livre são a base para a análise de dados no Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: ef2b452a0dcb2659b49fc0507b096952a89ea2f4
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 69%

---

# Tabela de forma livre

No Analysis Workspace, uma Tabela de forma livre é a base para a análise de dados interativa. Você pode arrastar e soltar uma combinação de [componentes](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/analysis-workspace-components.html?lang=pt-BR) em linhas e colunas para criar uma tabela personalizada para sua análise. À medida que cada componente é descartado, a tabela é atualizada imediatamente, para que você possa analisar e pesquisar mais fundo rapidamente.

## Criar uma tabela de forma livre simples

Você começa com uma Tabela de forma livre vazia.

![Tabela de forma livre vazia](assets/freeform-table-1.png)

Se soltar a **[!UICONTROL ** Visitas **]** na métrica **[!UICONTROL ** Solte uma métrica aqui (ou qualquer outro componente)**]**, a Tabela de forma livre é preenchida automaticamente com visitas por dia no período de calendário selecionado.

![Tabela de forma livre de visitas](assets/freeform-table-2.png)

Em seguida, solte o **[!UICONTROL ** Página **]** para substituir a dimensão **[!UICONTROL ** Dia **]** , a tabela de forma livre reflete automaticamente as visitas de cada página.

![Tabela de forma livre de visitas por página](assets/freeform-table-3.png)

É possível detalhar, por exemplo, a variável **[!UICONTROL ** categoria:5 **]** ao soltar a página **[!UICONTROL ** Canal de marketing **]** na dimensão **[!UICONTROL ** categoria:5 **]** linha.

![Detalhamento de visitas por tabela de forma livre de página](assets/freeform-table-4.png)


## Tabelas automatizadas

Como ilustrado acima, a maneira mais rápida de criar uma tabela é soltar componentes diretamente em um projeto, painel ou tabela de forma livre em branco. Uma tabela de forma livre será criada automaticamente para você em um formato recomendado. [Assista ao tutorial](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace.html?lang=pt-BR).

![](assets/automated-table.png)

## Construtor de tabelas de forma livre

Se preferir adicionar primeiro vários componentes à tabela e, em seguida, renderizar os dados, ative o Construtor de tabelas de forma livre. Com o construtor ativado, você pode arrastar e soltar em muitas dimensões, detalhamentos, métricas e segmentos para criar tabelas que respondam a perguntas mais complexas. Os dados não serão atualizados dinamicamente, serão atualizados assim que você clicar **[!UICONTROL Criar]**.

![](assets/table-builder.png)

## Interações de tabela

É possível personalizar e interagir com uma tabela de forma livre de várias maneiras:

* **Linhas**
   * Você pode ajustar mais linhas em uma única tela ajustando a [densidade de visualização](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/view-density.html?lang=pt-BR) do projeto.
   * Cada linha da dimensão pode exibir até 400 linhas antes que ocorra paginação. Clique no número ao lado de &quot;Linhas&quot; para mostrar mais linhas em uma página. Navegue até uma página diferente usando a seta de página no cabeçalho.
   * As linhas podem ser detalhadas por componentes adicionais. Para detalhar várias linhas ao mesmo tempo, basta selecionar várias linhas e arrastar o próximo componente na parte superior das linhas selecionadas. Saiba mais sobre [detalhamentos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.html?lang=pt-BR).
   * As linhas podem ser [filtradas](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.html?lang=pt-BR) para mostrar um conjunto reduzido de itens. Configurações adicionais estão disponíveis em [Configurações de linha](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.html?lang=pt-BR).

* **Colunas**
   * Os componentes podem ser empilhados dentro de colunas para criar métricas segmentadas, análise entre guias e muito mais.
   * A exibição de cada coluna pode ser ajustada nas [configurações de coluna](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=pt-BR).
   * Várias ações estão disponíveis no [menu acionado via clique com o botão direito do mouse](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/using-the-right-click-menu.html?lang=pt-BR). O menu fornece ações diferentes a depender se você clicar no cabeçalho da tabela, nas linhas ou nas colunas.

## Exportar dados da tabela de forma livre

Saiba mais sobre todos os dados de [opções de exportação](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=pt-BR) do Analysis Workspace.

* Clique com o botão direito do mouse em > **[!UICONTROL Copiar dados para a área de transferência]** para exportar os dados da tabela exibidos. Se uma seleção de tabela for feita, essa opção indicará **[!UICONTROL Copiar seleção para a área de transferência]**. A tecla de atalho **Ctrl + C** também copia os dados selecionados.
* Clique com o botão direito do mouse em > **[!UICONTROL Baixar dados como CSV]** para baixar os dados da tabela exibidos como um CSV. Se uma seleção de tabela for feita, essa opção indicará **[!UICONTROL Baixar seleção como CSV]**.
* Clique com o botão direito do mouse em > **[!UICONTROL Projeto > Baixar itens como CSV]** exporta até 50.000 itens de dimensão para a dimensão selecionada.

Saiba mais sobre todos os dados de [opções de exportação](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?lang=pt-BR) do Analysis Workspace.

![](assets/export-options.png)

## Vídeos

Visão geral do construtor de Tabelas de forma livre:

>[!VIDEO](https://video.tv.adobe.com/v/31318/?quality=12)

Filtros de Tabela de forma livre:

>[!VIDEO](https://video.tv.adobe.com/v/23232/?quality=12)

Totais de Tabelas de forma livre:

>[!VIDEO](https://video.tv.adobe.com/v/29273/?quality=12)
