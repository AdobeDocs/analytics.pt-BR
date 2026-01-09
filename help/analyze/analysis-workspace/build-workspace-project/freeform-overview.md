---
description: Saiba como trabalhar com projetos no Analysis Workspace. Use o gerenciador de projetos para gerenciar (criar, excluir, mover, compartilhar, aprovar, fixar, copiar e marcar) projetos.
keywords: Analysis Workspace
title: Visão geral dos projetos
feature: Workspace Basics
role: User, Admin
exl-id: 75c551de-297e-4c45-95e6-77472be6628a
source-git-commit: f02b660b551f5291443b8f7c5c51179a06b22eb9
workflow-type: tm+mt
source-wordcount: '1680'
ht-degree: 91%

---

# Visão geral dos projetos

Os projetos do Workspace permitem combinar painéis, visualizações e componentes para criar e compartilhar a sua análise com qualquer pessoa da sua organização. Antes de iniciar o seu primeiro projeto, saiba como acessar, navegar e gerenciar os projetos.

Para acessar projetos na Adobe Analytics, selecione **[!UICONTROL Workspace]**.  O gerenciador de **[!UICONTROL Projetos]** lista todos os projetos que você possui ou que foram compartilhados com você. O Gerenciador de projetos com a lista Projeto também é a página inicial padrão do Adobe Analytics, a menos que você tenha configurado o contrário em Preferências.

![Página de destino dos projetos, mostrando a lista de projetos.](assets/projects.png)


## Área de título

Na área de título ➊, você pode criar um projeto, criar uma pasta, editar as suas preferências e mostrar ou ocultar um painel com blocos adicionais.

* Para mostrar ou ocultar um painel esquerdo que permita selecionar entre **[!UICONTROL Projetos]** e **[!UICONTROL Aprendizagem]**, selecione ![Painel](/help/assets/icons/Rail.svg).
* O título mostra os projetos, opcionalmente adicionados com um caminho para a pasta selecionada. Por exemplo, [!UICONTROL Projetos] > **[!UICONTROL Pasta da empresa]**. Você pode selecionar partes individuais da subpasta para ir diretamente à pasta específica.
* Para mostrar blocos de um [**[!UICONTROL Projeto em branco]**](create-projects.md), [**[!UICONTROL Cartão de pontuação móvel em branco]**](/help/analyze/mobile-app/create-scorecard.md), **[!UICONTROL Abra a documentação]** e **[!UICONTROL Abra as notas de versão]**, selecione ![DivisaInativa](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar mais]**. Para ocultar a área com blocos, selecione ![ChevronDown](/help/assets/icons/ChevronDown.svg) **[!UICONTROL Mostrar menos]**.
* Com base no que você escolher mostrar, usando o [Seletor de exibição](#show-selector), é possível editar preferências e realizar ações na pasta atual visível em **[!UICONTROL Projetos]**:

  | Ação | Descrição |
  |---|---|
  | **[!UICONTROL Criar projeto]** | Selecione para [criar um novo projeto](create-projects.md). |
  | **[!UICONTROL Criar pasta]** | Selecione para [criar uma nova pasta](workspace-folders/create-folders.md). |
  | ![UserAdmin](/help/assets/icons/UserAdmin.svg) **[!UICONTROL Editar preferências]** | [Editar preferências](/help/analyze/analysis-workspace/user-preferences.md) de todos os seus projetos. Quando a navegação estrutural resulta em um espaço limitado, esta ação faz parte do submenu ![Mais](/help/assets/icons/More.svg). |
  | **[!UICONTROL Adicionar projetos]** | Selecione para [adicionar projetos](workspace-folders/add-projects.md) à pasta atual. Quando a navegação estrutural resulta em um espaço limitado, esta ação faz parte do submenu ![Mais](/help/assets/icons/More.svg). |
  | **[!UICONTROL Renomear pasta]** | [Renomeia](workspace-folders/manage-folders.md#rename-folders) a pasta atual. |
  | **[!UICONTROL Mover pasta]** | [Move](workspace-folders/manage-folders.md#move-folders) a pasta atual. |
  | **[!UICONTROL Excluir pasta]** | [Exclui](workspace-folders/manage-folders.md#delete-folders) a pasta atual. |




## Lista de projetos


A lista de projetos ➋ exibe todos os projetos que você possui e que foram compartilhados com você. A lista tem as seguintes colunas:

| Coluna | Descrição |
| --- | --- |
| ![SelectBox](/help/assets/icons/SelectBox.svg) | Quando um ou mais projetos são selecionados, uma barra de ação azul aparece na parte inferior da interface “Projeto”. Consulte [Ações](#actions) para mais detalhes. |
| ![StarOutline](/help/assets/icons/StarOutline.svg) | Selecione ![Star](/help/assets/icons/Star.svg) para adicionar ou ![StarOutline](/help/assets/icons/StarOutline.svg) para remover um projeto dos favoritos. |
| **[!UICONTROL Título e descrição]** | Para editar o projeto, selecione o link do título, que abrirá o [projeto do Workspace](/help/analyze/analysis-workspace/home.md). Projetos compartilhados com você são indicados com ![Compartilhar](/help/assets/icons/ShareAlt.svg). Selecione ![InfoOutline](/help/assets/icons/InfoOutline.svg) para exibir um menu pop-up com mais detalhes sobre o projeto. Selecione ![Mais](/help/assets/icons/More.svg) para abrir um menu de contexto com ações. Consulte [Ações](#actions) para mais detalhes. |
| **[!UICONTROL Tipo]** | Um projeto do Workspace, uma pasta ![FolderUser](/help/assets/icons/FolderUser.svg) ou um [cartão de pontuação móvel](/help/analyze/mobile-app/home.md). |
| **[!UICONTROL Tags]** | As tags aplicadas ao projeto.  |
| **[!UICONTROL Programado]** | Se um projeto está agendado para ser enviado por email aos destinatários. As opções são ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ativado]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Desativado]**. Consulte [Enviar dados do projeto a outras pessoas](/help/analyze/analysis-workspace/curate-share/t-schedule-report.md). |
| **[!UICONTROL Link compartilhado (qualquer pessoa)]** | Se um projeto é compartilhado com alguém, mesmo com pessoas que não tenham acesso ao Analysis Workspace. As opções são ![StatusGreen](/help/assets/icons/StatusGreen.svg) **[!UICONTROL Ativo]** ou ![StatusGray](/help/assets/icons/StatusGray.svg) **[!UICONTROL Inativo]**. Consulte [Compartilhar um projeto com qualquer pessoa (sem necessidade de logon)](/help/analyze/analysis-workspace/curate-share/share-projects.md#share-a-project-with-anyone-no-login-required) em [Compartilhar projetos](/help/analyze/analysis-workspace/curate-share/share-projects.md) para mais informações. |
| **[!UICONTROL Função do projeto]** | A sua função no projeto. As opções são: editar, duplicar e exibir. Consulte [Funções do projeto](/help/analyze/analysis-workspace/curate-share/curate.md) para mais informações. |
| **[!UICONTROL Conjunto de relatórios]** | O conjunto de relatórios ao qual o projeto está associado. |
| **[!UICONTROL Proprietário]** | A pessoa que criou o projeto (você ou alguém que compartilhou o projeto com você.) |
| **[!UICONTROL Compartilhado com]** | Usuários com os quais o projeto foi compartilhado. |
| **[!UICONTROL Última modificação]** | Data e hora em que o projeto foi modificado pela última vez. |
| **[!UICONTROL Aberto pela última vez]** | Data e hora da última vez que o projeto foi aberto. |
| **[!UICONTROL ID de componente]** | A ID do componente. |
| **[!UICONTROL Intervalo de datas mais longo]** | O intervalo de datas mais longo de qualquer um dos painéis ou visualizações do projeto. |
| **[!UICONTROL Número de consultas]** | A quantidade total de consultas contidas no projeto. |
| **[!UICONTROL Localização]** | A pasta na qual o projeto reside. |

Passe o mouse sobre qualquer cabeçalho de coluna para exibir ![ChevronDown](/help/assets/icons/ChevronDown.svg) e selecione no menu de contexto:

* **[!UICONTROL Classificação crescente]**
* **[!UICONTROL Classificação decrescente]**
* **[!UICONTROL Redimensionar coluna]**. Uma linha azul aparece para ajudar a redimensionar a coluna.

### Ações

É possível realizar ações em um ou mais projetos por meio do menu de contexto ![Mais](/help/assets/icons/More.svg) ou da barra de ação azul.

| Ícone | Ação | Descrição |
|:---:| ---|---|
| ![CrossSize75](/help/assets/icons/Close.svg) | **[!UICONTROL *x *selecionado(s)]** | Desmarque os projetos e pastas selecionados, e remova a barra de ação azul. |
| ![Excluir](/help/assets/icons/Delete.svg) | **[!UICONTROL Excluir]** | Exclua um ou mais projetos ou pastas. Uma confirmação será solicitada. <p>Projetos que você exclui:</p><ul><li>Não podem ser recuperados</li><li>São removidos da lista de projetos</li><li>Não podem mais ser acessado pelo URL</li><li>Não estão mais incluídos em entregas agendadas (nos casos em que foram configurados anteriormente para entregas agendadas)<br/>Para obter informações sobre entregas agendadas, consulte [Projetos agendados](/help/components/scheduled-projects-manager.md).  </p> |
| ![Compartilhar](/help/assets/icons/ShareAlt.svg) | **[!UICONTROL Compartilhar]** | Compartilhar um projeto. Consulte [Compartilhar um projeto](/help/analyze/analysis-workspace/curate-share/share-projects.md) para mais informações. |
| ![Editar](/help/assets/icons/Edit.svg) | **[!UICONTROL Renomear]** | Renomear um projeto. Abre uma caixa de diálogo **[!UICONTROL Renomear: *nome do projeto *]**. Digite o novo nome e selecione&#x200B;**[!UICONTROL Salvar &#x200B;]**. |
| ![Copiar](/help/assets/icons/Copy.svg) | **[!UICONTROL Copiar]** | Copiar um ou mais projetos. O projeto tem os mesmos nome e sufixo `(Copy)`. |
| ![PinOnff](/help/assets/icons/PinOff.svg) | **[!UICONTROL Fixar]** ou **[!UICONTROL Desafixar]** | Fixar ou desafixar um ou mais projetos ou pastas. Os projetos e pastas fixados aparecem na parte superior da lista, e ignoram a ordem de classificação especificada. |
| ![ArrowUp](/help/assets/icons/ArrowUp.svg) | **[!UICONTROL Mover para cima]** | Mover um projeto ou uma pasta fixada para cima na lista de projetos. |
| ![ArrowDown](/help/assets/icons/ArrowDown.svg) | **[!UICONTROL Mover para baixo]** | Mover um projeto ou uma pasta fixada para baixo na lista de projetos. |
| ![Rótulo](/help/assets/icons/Label.svg) | **[!UICONTROL Tag]** | Marcar um ou mais projetos ou pastas com tags. A caixa de diálogo **[!UICONTROL Componentes das tags]** é exibida para a seleção de uma ou mais tags. Clique em **[!UICONTROL Salvar]** para salvar as tags dos projetos ou pastas selecionadas. |
| ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg) | **[!UICONTROL Aprovar]** ou **[!UICONTROL Desaprovar]** | Aprovar ou desaprovar um projeto. Somente administradores podem aprovar projetos. |
| ![FileCSV](/help/assets/icons/FileCSV.svg) | **[!UICONTROL Exportar CSV]** | Exportar os projetos selecionados como um arquivo CSV com o nome `Project List.csv`. |
| ![ProjectAdd](/help/assets/icons/ProjectAdd.svg) | **[!UICONTROL Adicionar projetos]** | Adicionar um ou mais projetos a uma pasta selecionada. Em **[!UICONTROL Adicionar projetos]**, é possível selecionar um ou mais projetos. Clique em **[!UICONTROL Adicionar]** para adicionar os projetos à pasta. Consulte [Adicionar projetos a pastas](workspace-folders/add-projects.md#from-inside-a-folder) para mais informações. |
| ![FolderAddTo](/help/assets/icons/FolderAddTo.svg) | **[!UICONTROL Mover para]** | Mover um ou mais projetos selecionados para uma pasta. Em **[!UICONTROL Selecionar pasta]**, selecione a pasta para a qual deseja mover o projeto selecionado e clique em **[!UICONTROL Mover]**. Consulte [Adicionar projetos a pastas](workspace-folders/add-projects.md#from-the-project-list) para mais informações. |



## Seletor de exibição

É possível alternar a aparência da interface de projetos por meio dos seletores **[!UICONTROL Mostrar]** ➌. O seletor **[!UICONTROL Mostrar]** define quais opções estão disponíveis na [Área de título](#title-area) e quais colunas são exibidas na [Lista de projetos](#project-list).

* Para alterar as opções disponíveis para a [Área de título](#title-area), selecione **[!UICONTROL Mostrar]** **[!UICONTROL Todos os projetos]** ou **[!UICONTROL Mostrar]** **[!UICONTROL Pastas e projetos]**.

* Para definir quais colunas você quer exibir para a [Lista de projetos](#project-list), selecione ![ColumnSetting](/help/assets/icons/ColumnSetting.svg) e, na caixa de diálogo **[!UICONTROL Personalizar tabela]**, marque ou desmarque colunas. Selecione **[!UICONTROL Aplicar]** para aplicar a personalização. Consulte [Lista de projetos](#project-list) para mais detalhes sobre as colunas.

## Painel de filtro

É possível filtrar os projetos e pastas da [Lista de projetos](#project-list) por meio do painel de filtros ➍. Para mostrar ou ocultar o painel de filtro, use ![Filtro](/help/assets/icons/Filter.svg).

O painel de filtro consiste nas seções a seguir.

### Tags

| Tags | Descrição |
|---|---|
| ![Tags](assets/projects-filters-tags.png){width="300"} | A seção **[!UICONTROL Tags]** permite filtrar por tags. <ul><li>Utilize ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar tags* para procurar as tags que deseja usar para filtrar.</li><li>É possível selecionar mais de uma tag. As tags disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**2︎⃣**: a quantidade de tags disponíveis para os projetos resultantes do filtro atual.</li><li>7︎⃣: a quantidade de projetos associados à tag específica.</li></ul></li></ul> |


### Conjuntos de relatórios

| Conjuntos de relatórios | Descrição |
|---|---|
| ![Conjunto de relatórios](assets/projects-filters-reportsuites.png){width="300"} | A seção **[!UICONTROL Conjuntos de relatórios]** permite filtrar por conjuntos de relatórios. <ul><li>Você usa ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar Conjuntos de Relatórios* para procurar conjuntos de relatórios que deseja usar para filtrar.</li><li>É possível selecionar mais de um conjunto de relatórios. Os conjuntos de relatórios disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**3︎⃣**: o número de conjuntos de relatórios disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: o número de projetos associados ao conjunto de relatórios específico.</li></ul></li></ul> |


### Proprietários

| Proprietário | Descrição |
|---|---|
| ![Proprietários](assets/projects-filters-owners.png){width="300"} | A seção **[!UICONTROL Proprietário]** permite filtrar por proprietários. <ul><li>Use ![Pesquisar](/help/assets/icons/Search.svg) *Pesquisar proprietários* para procurar os proprietários que deseja usar para filtrar.</li><li>É possível selecionar mais de um proprietário. Os proprietários disponíveis dependem das seleções feitas em outras seções no painel de filtro.</li><li>Os números indicam:<ul><li>**3︎⃣**: a quantidade de proprietários disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: a quantidade de projetos associados ao proprietário específico.</li></ul></li></ul> |


### Tipo

| Tipo | Descrição |
|---|---|
| ![Tipo](assets/projects-filters-type.png){width="300"} | A seção **[!UICONTROL Tipo]** permite filtrar por tipo de projeto ou pasta.<ul><li>Você pode selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL pasta]**</li><li>**[!UICONTROL Projeto do Espaço de trabalho]**</li><li>**[!UICONTROL Cartão de pontuação para dispositivos móveis]**</li></ul> <li>É possível selecionar vários outros filtros. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**5︎⃣**: a quantidade de outros filtros disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: a quantidade de projetos associados ao outro filtro específico.</li></ul></li></ul> |


### Outros filtros

| Outros filtros | Descrição |
|---|---|
| ![Outros filtros](assets/projects-filters-others.png){width="300"} | A seção **[!UICONTROL Outros filtros]** permite filtrar por outros filtros predefinidos.<ul><li>Você pode selecionar uma ou mais das seguintes opções:<ul><li> **[!UICONTROL Exibir tudo]**</li><li>**[!UICONTROL Compartilhado comigo]**</li><li>**[!UICONTROL Meu]**</li><li>**[!UICONTROL Aprovado]**</li><li>**[!UICONTROL Favoritos]**</li></ul> O que você pode selecionar depende da sua função e das suas permissões.</li><li>É possível selecionar vários outros filtros. Os outros filtros disponíveis dependem das seleções feitas em outras seções no painel de filtros.</li><li>Os números indicam:<ul><li>**5︎⃣**: a quantidade de outros filtros disponíveis para os projetos resultantes do filtro atual.</li><li>4︎⃣: a quantidade de projetos associados ao outro filtro específico.</li></ul></li></ul> |

## Pesquisar

Use a área de pesquisa ➎ para procurar projetos e pastas com o campo ![Pesquisar](/help/assets/icons/Search.svg). Comece a digitar, e a [lista de projetos](#project-list) filtrará automaticamente conforme a sua pesquisa.

A área de pesquisa também mostra os filtros aplicados do painel de filtro.

* Para remover um filtro, selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) no filtro.
* Para remover todos os conjuntos de dados selecionados, clique em “Limpar tudo”.

Se o espaço for limitado para exibir os filtros individuais, você verá **[!UICONTROL Segmentando com *x* filtros]**.

* Para remover um filtro:

   1. Use **[!UICONTROL *x *filtros]**![ChevronDown](/help/assets/icons/ChevronDown.svg) para abrir um menu de contexto com os tipos de filtro e os filtros individuais.
   1. Selecione ![CrossSize75](/help/assets/icons/CrossSize75.svg) para remover um filtro.

