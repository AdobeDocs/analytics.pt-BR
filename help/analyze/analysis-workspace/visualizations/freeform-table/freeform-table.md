---
title: Tabela de forma livre
description: As tabelas de forma livre são a base para a análise de dados no Workspace
feature: Freeform Tables
role: User, Admin
exl-id: 7a0432f9-2cab-47be-bbd6-ede96cb840a3
source-git-commit: bb3e8b030af78f0d7758b4cff41d66f20695e11e
workflow-type: ht
source-wordcount: '785'
ht-degree: 100%

---

# Tabela de forma livre {#freeform-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_freeformtable_button"
>title="Tabela de forma livre"
>abstract="Crie uma visualização de tabela de forma livre vazia que você pode criar usando dimensões, segmentos, métricas e intervalos de datas. Você pode usar a tabela de forma livre como base para outras visualizações."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Este artigo é sobre a visualização da tabela de forma livre no_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulte [Tabela de forma livre](https://experienceleague.adobe.com/pt-br/docs/analytics-platform/using/cja-workspace/visualizations/freeform-table/freeform-table) para ver a versão do_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**Customer Journey Analytics** deste artigo._

>[!ENDSHADEBOX]


No Analysis Workspace, a visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL tabela de forma livre]** é a base para a análise de dados interativa. Você pode arrastar e soltar uma combinação de [componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) em linhas e colunas para criar uma tabela personalizada para sua análise. À medida que solta cada componente, a tabela é atualizada de imediato, para que você possa analisar e encontrar detalhes rapidamente.

![Tabela de forma livre exibindo componentes em linhas e colunas, incluindo visitas e pedidos online de várias páginas da web.](assets/opening-section.png)

Para criar e configurar uma [!UICONTROL tabela de forma livre]:

* Adicione uma visualização de ![Tabela](/help/assets/icons/Table.svg) **[!UICONTROL tabela de forma livre]**. Consulte [Adicionar uma visualização a um painel](../freeform-analysis-visualizations.md#add-visualizations-to-a-panel).

## Tabelas automatizadas

A maneira mais rápida de criar uma tabela é soltar os componentes diretamente em um projeto, painel ou tabela de forma livre em branco. Isso cria uma tabela de forma livre em um formato recomendado. [Assista ao tutorial](https://experienceleague.adobe.com/pt-br/docs/analytics-learn/tutorials/analysis-workspace/building-freeform-tables/auto-build-freeform-tables-in-analysis-workspace).

![Um novo painel com o componente de visitas solto no espaço de trabalho.](assets/automated-table.png)

## Construtor de tabelas de forma livre

Se preferir adicionar vários componentes à tabela primeiro e depois renderizar os dados, selecione **[!UICONTROL Habilitar construtor de tabelas]**. Com o construtor habilitado, é possível arrastar e soltar dimensões, detalhamentos, métricas e filtros para criar tabelas que respondam a perguntas mais complexas. Os dados são atualizados ao clicar em **[!UICONTROL Criar]**.

![Um construtor de tabelas de forma livre exibindo ](assets/table-builder.png)

## Interações

É possível personalizar e interagir com uma tabela de forma livre de várias maneiras:

### Filtrar e classificar

* É possível [filtrar e classificar](filter-and-sort.md) os dados em uma tabela.

### Linhas

* [Crie rapidamente uma nova visualização](../freeform-analysis-visualizations.md#visualize) de uma ou mais linhas usando ![GraphBarVerticalAdd](/help/assets/icons/GraphBarVerticalAdd.svg).
* Você pode ajustar mais linhas em uma única tela ajustando a [densidade de visualização](/help/analyze/analysis-workspace/build-workspace-project/view-density.md) do projeto.
* Cada linha da dimensão pode exibir até 400 linhas antes que ocorra paginação. Selecione o número ao lado de **[!UICONTROL Linhas]** no cabeçalho da primeira coluna para mostrar mais linhas em uma página. Navegue até uma página diferente usando ![ChevronRight](/help/assets/icons/ChevronRight.svg) no cabeçalho da primeira coluna.
* É possível detalhar as linhas por componentes adicionais. Para detalhar várias linhas ao mesmo tempo, selecione as linhas e arraste o próximo componente sobre elas. Saiba mais sobre [detalhamentos](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).
* As linhas podem ser [filtradas](/help/analyze/analysis-workspace/visualizations/freeform-table/filter-and-sort.md) para mostrar um conjunto reduzido de itens. Configurações adicionais estão disponíveis em [Configurações de linha](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md).

### Colunas

* Os componentes podem ser empilhados dentro de colunas para criar métricas filtradas, análise entre guias e muito mais.
* É possível ajustar a exibição de cada coluna nas [configurações de coluna](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/column-settings.md).
* Há várias ações disponíveis no [menu de contexto](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu). O menu fornece ações diferentes ao selecionar o cabeçalho da tabela, as linhas ou as colunas.


## Configurações 

Selecione ![Configuração](/help/assets/icons/Setting.svg) para exibir as **[!UICONTROL configurações da tabela]**. As [configurações](../freeform-analysis-visualizations.md#settings) de visualização específicas a seguir estão disponíveis:

### Fonte de dados

| Opção | Descrição |
|---|---|
| **[!UICONTROL Visualizações vinculadas]**. | Lista todas as visualizações vinculadas. |
| **[!UICONTROL Exibir fonte de dados]** | Quando desmarcada, a tabela de forma livre que funciona como fonte de dados para a visualização fica oculta no Workspace. |

### Configurações 

| Opção | Descrição |
|---|---|
| **[!UICONTROL Alinhar as datas de cada coluna para que todas iniciem na mesma linha]** | Determina se as datas de cada coluna serão alinhadas ou não, a fim de que todas comecem na mesma linha. |


## Menu de contexto

As opções do [menu de contexto](../freeform-analysis-visualizations.md#context-menu) a seguir estão disponíveis no cabeçalho da visualização:

| Opção | Descrição |
| --- | --- |
| **[!UICONTROL Inserir visualização copiada]**n | Cola (insere) uma visualização copiada em outro lugar no projeto, ou em um projeto completamente diferente. |
| **[!UICONTROL Copiar dados para a área de transferência]** | Copia dados da visualização para a área de transferência. |
| **[!UICONTROL Copiar seleção para a área de transferência]** | Copia a seleção da visualização para a área de transferência. |
| **[!UICONTROL Baixar itens como CSV (*nome da dimensão*)]** | Baixe imediatamente os itens de dimensão (até um máximo de 50.000) da visualização para o dispositivo local. Há um limite de 50.000 itens de dimensão para a dimensão selecionada. |
| **[!UICONTROL Copiar visualização]** | Copia a visualização para que você possa inseri-la em outro lugar no projeto, ou em um projeto completamente diferente. |
| **[!UICONTROL Baixar dados CSV]** | Baixe imediatamente os dados exibidos da visualização para o dispositivo local. |
| **[!UICONTROL Duplicar visualização]** | Cria uma duplicata exata da visualização. |
| **[!UICONTROL Editar descrição]** | Permite adicionar (ou editar) uma descrição de texto da visualização. Consulte [Texto](../text.md). |
| **[!UICONTROL Obter link da visualização]** | Copia um link direto da visualização para compartilhamento. A caixa de diálogo Compartilhar link exibe o link. Selecione Copiar para enviar o link para a área de transferência. |
| **[!UICONTROL Começar de novo]** | Exclui a configuração da visualização atual para que seja possível reconfigurá-la do zero. |



## Vídeos

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Visão geral do construtor de tabelas de forma livre](https://video.tv.adobe.com/v/31318?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Filtros de tabela de forma livre](https://video.tv.adobe.com/v/23232?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Totais da tabela de forma livre](https://video.tv.adobe.com/v/29273?quality=12&learn=on){target="_blank"} para assistir a um vídeo de demonstração.

>[!ENDSHADEBOX]


>[!MORELIKETHIS]
>
>[Adicionar uma visualização a um painel](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel)
>[Configurações de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#settings)
>[Menu de contexto de visualização](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#context-menu)
>



