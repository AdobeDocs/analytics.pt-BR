---
description: 'null'
keywords: Analysis Workspace
title: Criar projeto - visão geral
topic: Reports and analytics
uuid: a68be05d-f31e-4e6d-ad04-c784ecb0eb00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Criar projeto - visão geral

**[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**

Você pode criar um projeto robusto do Analytics com base em uma combinação de exibições, componentes de relatórios e tabelas de dados. Ele adiciona muitos dos recursos do criador de tabelas da Ad Hoc Analysis ao Analytics.

No Analysis Workspace, você pode comparar e examinar os dados de maneiras que não eram possíveis anteriormente. Por exemplo, é possível configurar relatórios classificados e faça alterações iterativas imediatas à consulta de dados e acesse e manipule os valores no nível de relatório.

A consulta vai diretamente para o mecanismo de relatórios. É possível fazer alterações em linha com outros relatórios para criar a sua análise. Os resultados retornam imediatamente, sem nenhuma atualização do navegador.

## Página da lista de projetos da Workspace   {#section_39AA007D7C384F4E869F842F1C7B11F8}

When you first go to **[!UICONTROL Analytics]** > **[!UICONTROL Workspace]**, the page lists all the projects you own or have been granted access to. You can set this page to be your Adobe Analytics landing page by clicking **[!UICONTROL Set as Landing Page]**. (Se você não encontrar essa opção, como na captura de tela abaixo, ela já é sua página inicial).

![](assets/sample-project.png)

A página da lista de projeto do Workspace contém as informações a seguir:

| Elemento | Descrição |
|---|---|
| Projeto   [Modelos](/help/analyze/analysis-workspace/build-workspace-project/starter-projects.md) | Você pode usar esses modelos de projeto pré-preenchidos como estão ou adaptá-los às suas necessidades (adicionando ou substituindo métricas ou visualizações, por exemplo) e salvá-los com um novo nome. |
| [Criar novo projeto](/help/analyze/analysis-workspace/build-workspace-project/t-freeform-project.md) | Clique nesse link para criar um novo projeto a partir do zero. |
| Gerenciar projetos | Clicking this link takes you to the Projects Component Manager ( **[!UICONTROL Analytics]** > **[!UICONTROL Components]** > **[!UICONTROL Projects]**), which lists all your projects and lets you tag, share, delete, rename, approve, copy, and export projects to CSV. |
| Exibir tutoriais | O direciona para os [vídeos no YouTube do Analysis Workspace](https://www.youtube.com/playlist?list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS). |
| Nome | Nome do projeto do Workspace. |
| Criado por | A pessoa que criou o projeto (você ou alguém que compartilhou o projeto com você.) |
| Tags | Tags that were applied to the project, either in the Projects Component Manager or under **[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**. |
| Última modificação | Data e hora em que o projeto foi modificado pela última vez. |

## Informações e configurações do projeto {#section_63773D0B9E4543E88068ECECB9EEB4C6}

**[!UICONTROL Workspace]** > **[!UICONTROL Project]** > **[!UICONTROL Project Info & Settings]**

![](assets/projectinfo.png)

**[!UICONTROL Project Info & Settings]** fornece informações em nível de projeto sobre o projeto atualmente ativo.

| Configuração | Descrição |
|---|---|
| Nome do projeto | O nome fornecido ao projeto. Você pode clicar duas vezes no nome para editá-lo. |
| Criado por | Nome do proprietário do projeto |
| Última modificação | Data da última modificação do projeto. |
| Tags | Lista qualquer tag aplicada a um projeto para classificar com mais facilidade. Além disso, também é possível adicionar tags a projetos ao salvá-los. Exiba as de um projeto na Página inicial do Workspace na coluna [!UICONTROL Tags]Tags. |
| Descrição | Uma descrição é útil para esclarecer a finalidade de um projeto. Você pode clicar duas vezes na descrição para editá-la. |
| Contagem de instâncias repetidas no projeto | Especifica se as instâncias repetidas devem ser contadas nos relatórios. Se você tiver vários valores em sequência para a mesma variável, pode contá-las como uma ou várias instâncias dessa variável. |
| Esquema de cores da visualização | É possível alterar o esquema de cores utilizado no Workspace, escolhendo em uma paleta de cores diferente ou especificando sua própria paleta. Esse recurso afeta muitas coisas no Workspace, incluindo a maioria das visualizações. |
| Exibir densidade | Permite ver mais dados na tela, ao reduzir o preenchimento vertical do painel à esquerda, em tabelas de forma livre e de coorte. |

## Menu de projetos {#section_850CDFCB86A64EB0A0AD5B9E0FCB7013}

O menu superior de Projetos tem a seguinte aparência:

![](assets/new-project-menus.png)

O submenu contém as seguintes opções.

>[!NOTE] As opções marcadas com um asterisco (*) são exibidas somente em projetos **salvos**.

| Projeto | Editar | Inserir | Componentes | Compartilhar | Ajuda |
|---|---|---|---|---|---|
| Novo | Recurso Desfazer | Novo painel | Novo segmento | Compartilhar projeto | Vídeos |
| Abrir | Limpar | Novo painel de forma livre | Nova métrica | Obter link do projeto* | Teclas de atalho |
| Salvar | Limpar tudo | Novo painel de Comparação de segmentos | Novo intervalo de datas | Enviar arquivo agora* | Fórum de ajuda |
| Salvar como* |  | Nova tabela de forma livre | Novo alerta | Enviar arquivo agendado* |  |
| Definir como Página inicial* |  | Nova linha | Atualizar componentes | Preparar dados do projeto |  |
| Atualizar projeto |  | Nova barra |  |  |  |
| Baixar CSV |  |  |  |  |  |
| Baixar o PDF* |  |  |  |  |  |
| Informações e configurações do projeto |  |  |  |  |  |

## Trilho da esquerda   {#section_271295C26EC840ABB2A8E7EC0498B60E}

O painel da esquerda tem 3 ícones, que permitem acessar os Painéis, as [Visualizações](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md) e os [Componentes](/help/analyze/analysis-workspace/components/analysis-workspace-components.md) (Dimensões, Métricas, Segmentos, Intervalos de data) com um clique:

![](assets/panels.png) ![](assets/visualizations.png) ![](assets/components.png)

A **[!UICONTROL Blank Panel]** was added to the list of panels accessible from the left rail. Para criar um **novo Painel de coorte**, arraste um Painel em branco e solte-o em uma visualização de Tabela de coorte.
