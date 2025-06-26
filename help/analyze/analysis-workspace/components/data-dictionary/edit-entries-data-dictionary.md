---
description: O Dicionário de dados no Analysis Workspace permite que os usuários catalogem e acompanhem os vários componentes do Analysis Workspace, incluindo o uso pretendido, que está aprovado, quais são duplicatas e assim por diante.
title: Editar entradas no Dicionário de dados
feature: Components
role: Admin
exl-id: 4f15cad2-596e-41c3-89aa-4456d8e94fa0
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 85%

---

# Editar entradas de componente no dicionário de dados

Os administradores do Analytics podem editar entradas de componentes no Dicionário de dados de um determinado Conjunto de relatórios. Todas as alterações feitas ficam visíveis para todos os usuários do Conjunto de relatórios.

Para editar um componente no Dicionário de dados:

1. Vá para o projeto do Analysis Workspace que contém o componente que deseja editar.

1. Clique no ícone do **Dicionário de dados** no painel esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de Dados estão descritas em [Acessar o Dicionário de Dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md#access-the-data-dictionary).)

   A janela do dicionário de dados é exibida.

   ![Visualização do administrador do Dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o conjunto de relatórios correto está selecionado no menu suspenso. Por padrão, o conjunto de relatórios em que você já está é exibido.

1. (Opcional) No campo de pesquisa, comece a digitar o nome do componente que deseja editar.

   O tipo de componente pode ser identificado por cor e ícone. As **Dimensões** e o ![Ícone de dimensão](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Data_18_N.svg) são laranjas, os **Segmentos** e o ![Ícone de segmento](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Segmentation_18_N.svg) são azuis, os **Intervalos de datas** e o ![Ícone de intervalo de datas](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calendar_18_N.svg) são roxos e as **Métricas** e o ![Ícone de métrica](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Event_18_N.svg) são verdes. O ícone da Adobe indica um modelo de métrica calculada ou um modelo de segmento, e o ícone da calculadora, ![Ícone de calculadora](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Calculator_18_N.svg), indica uma métrica calculada que foi criada por um administrador do Analytics em sua organização.

1. (Opcional) Selecione o ícone de **Filtro** ![Ícone de filtro do dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Filter_18_N.svg) e, em seguida, selecione qualquer uma das seguintes opções para filtrar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | **[!UICONTROL Aprovado]** | Somente componentes marcados como Aprovado por um administrador. |
   | **[!UICONTROL Favoritos]** | Somente componentes que estão na lista de Favoritos. Para obter informações sobre como adicionar componentes à lista de favoritos, consulte [Visão geral dos componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md). |
   | **[!UICONTROL Dimensões]** | Somente componentes que sejam Dimensões. (Essa opção também está disponível na guia **[!UICONTROL Filtros rápidos]** ao acessar o dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Métricas]** | Somente componentes que sejam Métricas. (Essa opção também está disponível na guia **[!UICONTROL Filtros rápidos]** ao acessar o dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Segmentos]** | Somente componentes que são Segmentos. (Essa opção também está disponível na guia **[!UICONTROL Filtros rápidos]** ao acessar o dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Intervalos de datas]** | Somente componentes que sejam Intervalos de datas. (Essa opção também está disponível na guia **[!UICONTROL Filtros rápidos]** ao acessar o dicionário de dados pela primeira vez.) |
   | **[!UICONTROL Exibir tudo]** | Todos os componentes. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Não aprovado]** | Somente componentes que ainda não estão marcados como Aprovados por um administrador. Como administrador, isso é útil ao identificar componentes que exigem sua análise e aprovação. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Descrição ausente]** | Somente os componentes que ainda não têm uma descrição no campo Descrição. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Mostrar duplicatas]** | <p>Somente componentes que tenham o mesmo nome ou a mesma definição de outro componente no Conjunto de relatórios selecionado. Nomes ou definições precisam ser correspondências exatas para serem mostradas como duplicatas.</p><p>Essa opção está disponível somente para administradores.</p><p>**OBSERVAÇÃO:** para definições, isso inclui os componentes criados por você assim como os fornecidos pela Adobe. Para os nomes, isso atualmente inclui apenas os componentes criados por você e não os fornecidos pela Adobe. A exibição de nomes duplicados para componentes fornecidos pela Adobe será adicionada em uma versão posterior.</p> |
   | **[!UICONTROL Sem dados recentes]** | Somente componentes que não coletaram dados nos últimos 90 dias. Essa opção está disponível somente para administradores. |
   | **[!UICONTROL Criado por Adobe]** <!-- I don't see this option--> | Mostrar somente componentes que foram criados pelo Adobe.  Por exemplo, Adobe Target. Os componentes que foram criados por um administrador ou outro usuário em sua organização não são mostrados. |

   {style="table-layout:auto"}

1. (Opcional) Selecione o ícone de **Classificar**, ![Ícone de classificar componentes](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SortOrderDown_18_N.svg), e selecione qualquer uma das seguintes opções de filtro para classificar a lista de componentes:

   | Opção | Função |
   |---------|----------|
   | [!UICONTROL **Recomendado**] | Classifica componentes com aqueles recomendados no topo da lista. Os componentes usados com mais frequência e mais recentemente por você ou outras pessoas em sua organização são mostrados em uma posição superior na lista. |
   | [!UICONTROL **Ordem alfabética**] | Classifica os componentes em ordem alfabética. |
   | [!UICONTROL **Categórico**] | Classifica componentes de acordo com o tipo de componente (dimensão, métrica, segmento, intervalo de datas). |

   {style="table-layout:auto"}

1. Na lista de componentes, selecione o componente que deseja editar.

1. Clique no ícone de **Editar** ![ícone de Editar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_Edit_18_N.svg) ao lado do nome do componente.

1. Edite qualquer uma das seguintes informações sobre o componente:

   | Opção | Função |
   |---------|----------|
   | **[!UICONTROL Aprovado]** | <p>Indica que o componente foi revisado e aprovado pelo administrador.</p><p>Depois que um componente é aprovado, os administradores podem remover a aprovação clicando no botão **Aprovado**.</p> |
   | **[!UICONTROL Aprovação necessária]** | <p>Indica que o componente ainda não foi revisado e aprovado pelo administrador.</p><p>Os administradores veem uma opção para **[!UICONTROL Aprovar]**. Selecionar essa opção marca o componente como “Aprovado” para os usuários.</p> |
   | **[!UICONTROL Descrição]** | Descreve a função pretendida do componente. (Essas informações são adicionadas pelo administrador do Analytics, conforme descrito em [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).) |
   | **[!UICONTROL Frequentemente usado com]** | <p>Mostra os componentes mais usados com o componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Esta lista é baseada em dados dos últimos 90 dias. Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos **[!UICONTROL Sempre incluir]** e **[!UICONTROL Sempre excluir]**. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p> |
   | **[!UICONTROL Semelhante a]** | <p>Mostra componentes com nomes semelhantes ao componente que você está visualizando.</p><p>Até 5 componentes são mostrados nos 5 tipos de componentes principais: métrica, métrica calculada, dimensão, segmento e intervalo de datas.</p><p>Somente os componentes que você tem acesso para exibir são mostrados.</p><p>Qualquer componente duplicado em seu conjunto de relatórios também será exibido aqui. Os administradores do Analytics devem identificar e remover todos os componentes duplicados, conforme descrito em [Monitorar integridade do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).</p><p>Os administradores podem preparar os componentes que os usuários veem nesta seção selecionando os componentes desejados nos campos suspensos **[!UICONTROL Sempre incluir]** e **[!UICONTROL Sempre excluir]**. Antes de preparar os componentes que os usuários veem, aplique primeiro o filtro **Mostrar tudo** para garantir que você veja todos os componentes que não estão sendo compartilhados com você.<!-- Soon we will make it so any fields that an admin doesn't have access to will be greyed out, and then they can enable the Show all filter to make it editable. --></p><p>**OBSERVAÇÃO:** atualmente, a seção **Semelhante a** inclui apenas componentes criados por você e não os fornecidos pela Adobe. Os componentes fornecidos pela Adobe serão adicionados em uma versão posterior.</p> |
   | **[!UICONTROL Tags]** | Mostra todas as tags aplicadas ao componente. Os usuários com acesso de administrador podem adicionar tags ao editar o componente. |
   | **[!UICONTROL Tipo de componente]** | Lista o tipo de componente, seja uma dimensão, uma métrica, um segmento ou um intervalo de datas. |
   | **[!UICONTROL Criado por]** | Mostra o nome do usuário que criou o componente. |
   | **[!UICONTROL Pré-visualizar]** | Mostra uma pré-visualização de como o componente é exibido no Analysis Workspace. |
   | **[!UICONTROL Data da última modificação]** | Exibe o dia em que o componente foi modificado pela última vez. Esta seção é exibida durante a visualização de segmentos, métricas calculadas e intervalos de datas. |

   {style="table-layout:auto"}

1. Clique no ícone de **Salvar** ![ícone de Salvar Dicionário de dados](https://spectrum.adobe.com/static/icons/workflow_18/Smock_SaveFloppy_18_N.svg) para salvar as alterações.
