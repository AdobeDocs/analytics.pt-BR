---
description: O Dicionário de dados no Analysis Workspace permite que os usuários catalogem e rastreiem os vários componentes no Analysis Workspace, incluindo o uso pretendido, que são aprovados, que são duplicatas e assim por diante.
title: Visão geral do dicionário de dados
feature: Components
role: User, Admin
hide: true
hidefromtoc: true
source-git-commit: d8442f1ec8f35fbcda98b35070936677813ce330
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 0%

---

# Visão geral do dicionário de dados

{{release-limited-testing}}

O Dicionário de dados no Analysis Workspace ajuda os usuários e administradores a acompanharem e compreenderem melhor os componentes em seus ambientes do Analytics.

Os administradores do Analytics são responsáveis por preparar informações sobre cada componente no Dicionário de dados para torná-lo disponível aos usuários.

## Benefícios para os usuários

O Dicionário de dados ajuda os usuários a entender melhor cada componente que está disponível para eles.

As informações disponíveis no Dicionário de dados incluem:

* Função de um componente e uso pretendido

* Componentes normalmente usados com aquele que você está visualizando

* Componentes semelhantes àqueles que você está visualizando

* Se um componente é aprovado pelo administrador do sistema

Para obter informações sobre como acessar o Dicionário de dados e para obter detalhes sobre as informações que ele contém, consulte [Exibir informações do componente no Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Benefícios para administradores

O Dicionário de dados ajuda os administradores do sistema a acompanhar e preparar os componentes em seus ambientes do Analytics.

Veja a seguir algumas das maneiras como os administradores do Analytics podem usar o Dicionário de dados:

* Identificar componentes duplicados que precisam ser consolidados.

* Identifique componentes que não estão coletando dados para que possam ser atualizados ou excluídos.

* Identificar componentes que ainda não foram aprovados.

* Atualize as descrições dos componentes diretamente no Analysis Workspace. Todas as atualizações feitas nas descrições de componentes no Dicionário de dados são refletidas no Conjunto de relatórios.

   Da mesma forma, todas as atualizações feitas nas descrições de componentes no Conjunto de relatórios são refletidas no Analysis Workspace.

   Para obter mais informações sobre como adicionar descrições de componentes no Analysis Workspace ou em um Conjunto de relatórios, consulte [Adicionar descrições de componentes](/help/analyze/analysis-workspace/components/add-component-descriptions.md).

## Acessar o dicionário de dados

Você pode acessar o Dicionário de dados de qualquer uma das seguintes maneiras no Analysis Workspace:

* No **Dicionário de dados** no painel esquerdo.

   ![Ícone do Dicionário de dados no painel esquerdo](assets/data-dictionary-access-icon.png)

* No **Dicionário de dados** ícone no provedor de informações de um componente.

   ![Ícone do Dicionário de dados no provedor de informações](assets/data-dictionary-access-infopopover.png)
<!--update screenshot; this was taken from a mock-->

* No menu : [!UICONTROL **Ajuda**] > [!UICONTROL **Dicionário de dados**].

Para obter informações detalhadas sobre as várias opções disponíveis no Dicionário de dados, consulte [Exibir informações do componente no Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/view-data-dictionary.md).

## Atualizar e preparar o dicionário de dados

Os administradores do Analytics são responsáveis por manter um Dicionário de dados íntegro em sua organização, conforme descrito em [Monitorar integridade do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/monitor-data-dictionary-health.md).

Como parte desse processo, os administradores do Analytics podem editar informações sobre cada componente no dicionário de dados, conforme descrito em [Editar entradas de componente no Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).

## Mover, minimizar ou fechar o dicionário de dados

Ao abrir o Dicionário de dados (conforme descrito em [Acessar o dicionário de dados](#access-the-data-dictionary)), ela é exibida como uma janela sobre o Analysis Workspace.

Você pode manipular a janela Dicionário de dados de qualquer uma das seguintes maneiras:

* Arraste-o para qualquer área no Analysis Workspace

   Se você fechar e reabrir o Analysis Workspace, a janela Dicionário de dados permanecerá no local onde você a moveu pela última vez. <!--True?-->

* Minimize-o

   Quando minimizado, o Dicionário de dados aparece como uma guia azul no canto inferior direito do Analysis Workspace.

   Quando você seleciona a guia azul, o Dicionário de dados é aberto no componente que você estava visualizando recentemente.

* Feche-o
