---
description: O Dicionário de dados no Analysis Workspace permite que os usuários catalogem e acompanhem os vários componentes do Analysis Workspace, incluindo o uso pretendido, que está aprovado, quais são duplicatas e assim por diante.
title: Visão geral do dicionário de dados
feature: Components
role: User, Admin
exl-id: ecc62287-dc20-41b3-9430-f14ea9fc05e6
source-git-commit: 74ef4e73b6ed1e2a4ad498e2314af704acb6d8cb
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 68%

---


# Visão geral do dicionário de dados {#data-dictionary-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="component_datadictionary"
>title="Dicionário de dados"
>abstract="O Dicionário de dados ajuda usuários e administradores a rastrear e entender melhor os componentes em seus ambientes do Analytics. <br/>Os administradores do Analytics são responsáveis por preparar informações sobre cada componente no Dicionário de Dados."

<!-- markdownlint-enable MD034 -->


O dicionário de dados do Analysis Workspace ajuda usuários e admins a acompanhar e compreender melhor os componentes em seu ambiente do Analytics.

Os administradores do Analytics são responsáveis por preparar informações sobre cada componente no Dicionário de dados para disponibilizá-las aos usuários.


>[!BEGINSHADEBOX]

Consulte o ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Dicionário de dados do Analysis Workspace](https://video.tv.adobe.com/v/3418028/?quality=12&learn=on){target="_blank"} para ver um vídeo de demonstração.

>[!ENDSHADEBOX]



## Benefícios para os usuários

O dicionário de dados ajuda os usuários a entender melhor cada componente que está disponível para eles.

As informações disponíveis no dicionário de dados incluem:

* A função de um componente e o uso pretendido.

* Componentes normalmente usados com o que você está visualizando.

* Componentes semelhantes ao que você está visualizando.

* Se um componente é aprovado pelo administrador do sistema.

Para obter informações sobre como acessar o Dicionário de dados e obter detalhes sobre as informações que ele contém, consulte [Exibir informações de componente no Dicionário de dados](view-data-dictionary.md).

## Benefícios para administradores

O dicionário de dados ajuda os administradores do sistema a acompanhar e preparar os componentes em seu ambiente do Analytics.

Os administradores do Analytics podem usar o Dicionário de dados para estas finalidades:

* Identificar componentes duplicados que precisam ser consolidados.

* Identificar componentes que não estão coletando dados para que possam ser atualizados ou excluídos.

* Identificar componentes que ainda não foram aprovados.

* Atualizar as descrições dos componentes diretamente no Analysis Workspace. Todas as atualizações feitas nas descrições de componentes do dicionário de dados são refletidas na visualização de dados.

  Da mesma forma, todas as atualizações feitas nas descrições de componentes da visualização de dados são refletidas no Analysis Workspace.

  Para obter mais informações sobre como adicionar descrições de componentes no Analysis Workspace ou em uma visualização de dados, consulte [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Acessar o dicionário de dados

Você pode acessar o dicionário de dados de qualquer uma das seguintes maneiras no Analysis Workspace:

![Ícone do dicionário de dados no painel esquerdo](assets/data-dictionary-access.png)

* Do ![marcador](/help/assets/icons/Bookmark.svg) no painel de botões.



* Do ![marcador](/help/assets/icons/Bookmark.svg) dentro do popover de informações de um componente.


Para obter informações detalhadas sobre as várias opções disponíveis no Dicionário de dados, consulte [Exibir informações de componente no Dicionário de dados](view-data-dictionary.md).

## Atualizar e preparar o Dicionário de dados

Os administradores do Adobe Analytics são responsáveis por manter um Dicionário de Dados íntegro para sua organização, conforme descrito em [Monitorar integridade do dicionário de dados](monitor-data-dictionary-health.md).

Como parte desse processo, os administradores do Adobe Analytics podem editar informações sobre cada componente no dicionário de dados, conforme descrito em [Editar entradas de componentes no Dicionário de Dados](edit-entries-data-dictionary.md).

## Mover, minimizar ou fechar o dicionário de dados

Ao abrir o dicionário de dados (conforme descrito em [Acessar o dicionário de dados](#access-the-data-dictionary)), ele é exibido como uma janela sobre o Analysis Workspace.

Você pode manipular a janela do dicionário de dados de qualquer uma das seguintes maneiras:

* Arraste-a para qualquer área no Analysis Workspace

  Se você fechar e reabrir o Analysis Workspace, a janela do dicionário de dados permanecerá no local para onde você a moveu pela última vez. <!--True?-->

* Minimize a janela.

  Quando minimizado, o dicionário de dados aparece como uma guia azul no canto inferior direito do Analysis Workspace.

  Ao selecionar a guia azul, o dicionário de dados é aberto no componente que você estava visualizando recentemente.

* Feche a janela.


<!--
# Data Dictionary overview

The Data Dictionary in Analysis Workspace helps both users and administrators keep track of and better understand the components in their Analytics environment.   

Analytics administrators are responsible for curating information about each component in the Data Dictionary to make it available to users.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Data dictionary](https://video.tv.adobe.com/v/3418028?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


## Benefits for users

The Data Dictionary helps users gain a better understanding of each component that is available to them. 

Information available in the Data Dictionary includes: 

* A component's function and intended use

* Components typically used with the one you are viewing

* Components that are similar to the one you are viewing

* Whether a component is approved by the system administrator 

For information about how to access the Data Dictionary and for details about the information it contains, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Benefits for administrators

The Data Dictionary helps system administrators keep track of and curate the components in their Analytics environment. 

Following are some of the ways Analytics administrators can use the Data Dictionary: 

* Identify duplicate components that need to be consolidated.

* Identify components that aren't collecting any data so they can be either updated or deleted.

* Identify components that are not yet approved.

* Update component descriptions directly in Analysis Workspace. Any updates made to component descriptions in the Data Dictionary are reflected in the Report Suite.

  Similarly, any updates made to component descriptions in the Report Suite are reflected in Analysis Workspace.

  For more information about adding component descriptions in either Analysis Workspace or in a Report Suite, see [Add component descriptions](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Access the Data Dictionary

You can access the Data Dictionary in any of the following ways within Analysis Workspace:

* From the **Data Dictionary** icon in the left rail.

  ![Data Dictionary icon in the left rail](assets/data-dictionary-access-icon.png)

* From the **Data Dictionary** icon within the info popover of a component. 

  ![Data Dictionary icon in info popover](assets/data-dictionary-access-infopopover.png)


For detailed information about the various options available in the Data Dictionary, see [View component information in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Update and curate the Data Dictionary

Analytics administrators are responsible for maintaining a healthy Data Dictionary for their organization, as described in [Monitor Data Dictionary Health](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

As part of this process, Analytics administrators can edit information about each component in the data dictionary, as described in [Edit component entries in the Data Dictionary](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Move, minimize, or close the Data Dictionary

When you open the Data Dictionary (as described in [Access the Data Dictionary](#access-the-data-dictionary)), it displays as a window on top of Analysis Workspace. 

You can manipulate the Data Dictionary window in any of the following ways:

* Drag it to any area within Analysis Workspace 

  If you close and re-open Analysis Workspace, the Data Dictionary window remains in the location where you last moved it.

* Minimize it

  When minimized, the Data Dictionary appears as a blue tab in the lower-right corner of Analysis Workspace.

  When you select the blue tab, the Data Dictionary opens to the component you were most recently viewing. 

* Close it

-->