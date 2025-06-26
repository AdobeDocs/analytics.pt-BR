---
description: O dicionário de dados do Analysis Workspace permite que os usuários rastreiem e criem um catálogo dos vários componentes no Analysis Workspace, incluindo seu uso pretendido, quais estão aprovados, quais são duplicatas e assim por diante.
title: Exibir o dicionário de dados
feature: Components
role: User, Admin
exl-id: 68f68ea4-f0a6-4937-bf8f-aecfa28572bb
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 98%

---

# Exibir informações de componente no dicionário de dados

O Dicionário de dados permite visualizar informações sobre um componente, incluindo a descrição do componente, componentes semelhantes, outros componentes com os quais um componente é usado com frequência e muito mais.

Para exibir informações sobre um componente no Dicionário de dados:

1. Acesse o projeto do Analysis Workspace que contém o componente que deseja visualizar.

1. Clique no ícone do [!UICONTROL **Dicionário de dados**] no painel esquerdo do Analysis Workspace. (As formas alternativas de acessar o Dicionário de Dados estão descritas em [Acessar o dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary).)

   A janela do dicionário de dados é exibida.

   ![data-dictionary.png](assets/data-dictionary.png)

   <!--double-check this screenshot. I mocked the admin view up a bit to get rid of the Dictionary health tab.-->

1. Verifique se o Conjunto de relatórios que contém o componente que você deseja visualizar está selecionado no menu suspenso. Por padrão, o conjunto de relatórios em que você já está é exibido.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja visualizar.

   O tipo de componente pode ser identificado por cor e ícone. As **Dimensões** e o ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranjas, os **Segmentos** e o ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, os **Intervalos de datas** e o ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e as **Métricas** e o ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone da Adobe indica um modelo de métrica calculada ou um modelo de segmento, e o ícone da calculadora, ![Ícone de calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg), indica uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | Mostrar somente componentes marcados como Aprovado por um administrador. |
   | [!UICONTROL **Favoritos**] | Mostrar somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | [!UICONTROL **Dimensões**] | Mostrar somente componentes que são dimensões. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Métricas**] | Mostrar somente componentes que são métricas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Segmentos**] | Mostrar somente componentes que são segmentos. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Intervalos de datas**] | Mostrar somente componentes que são intervalos de datas. (Essa opção também está disponível na guia [!UICONTROL **Filtros rápidos**] ao acessar o dicionário de dados pela primeira vez.) |
   | [!UICONTROL **Exibir tudo**] | Mostrar todos os componentes. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Não aprovado**] | Mostrar somente componentes que ainda não foram marcados como Aprovado por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Descrição ausente**] | Mostrar somente componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Mostrar duplicatas**] | <p>Mostrar somente componentes que tenham o mesmo nome ou a mesma definição de outro componente no conjunto de relatórios selecionado. Nomes ou definições precisam ser correspondências exatas para serem mostradas como duplicatas.</p><p>Essa opção está disponível somente para administradores.</p><p>**OBSERVAÇÃO:** para definições, isso inclui os componentes criados por você assim como os fornecidos pela Adobe. Para os nomes, isso atualmente inclui apenas os componentes criados por você e não os fornecidos pela Adobe. A exibição de nomes duplicados para componentes fornecidos pela Adobe será adicionada em uma versão posterior.</p> |
   | [!UICONTROL **Sem dados recentes**] | Mostrar somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | [!UICONTROL **Criado por Adobe**] <!-- I don't see this option--> | Mostrar somente componentes que foram criados pela Adobe. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

1. (Opcional) Selecione o ícone de **Classificar**, ![Ícone de classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   {{components-sort-options}}

1. Na lista de componentes, selecione o componente que deseja visualizar.

   As seguintes informações sobre o componente são exibidas:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Aprovado**] | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Depois que um componente é aprovado, os administradores podem remover a aprovação clicando no botão **Aprovado**.</p> |
   | [!UICONTROL **Aprovação necessária**] | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para [!UICONTROL **Aprovar**]. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
   | [!UICONTROL **Descrição**] | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | [!UICONTROL **Frequentemente usado com**] | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | [!UICONTROL **Semelhante a**] | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Qualquer componente duplicado em seu conjunto de relatórios também será exibido aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos [!UICONTROL **Sempre incluir**] e [!UICONTROL **Sempre excluir**]. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
   | [!UICONTROL **Tags**] | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
   | [!UICONTROL **Tipo de componente**] | Lista o tipo de componente, seja uma dimensão, uma métrica, um segmento ou um intervalo de datas. |
   | [!UICONTROL **Criado por**] | Mostra o nome do usuário que criou o componente. |
   | [!UICONTROL **Pré-visualizar**] | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
   | [!UICONTROL **Data da última modificação**] | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida durante a visualização de segmentos, métricas calculadas e intervalos de datas. |

   {style="table-layout:auto"}

1. (Opcional) Arraste um componente do Dicionário de dados para o Analysis Workspace.
