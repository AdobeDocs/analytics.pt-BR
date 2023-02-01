---
description: Os administradores são responsáveis por monitorar a integridade do Dicionário de dados. Isso inclui se os componentes estão coletando dados, se estão aprovados, se contêm descrições e estão livres de duplicatas.
title: Monitorar integridade do dicionário de dados
feature: Components
role: Admin
source-git-commit: 5bfbc3059526527e35f26b750d048efebee68e9e
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Monitorar integridade do dicionário de dados

{{release-limited-testing}}

Os administradores do Analytics são responsáveis por manter um Dicionário de dados saudável.

## Características de um dicionário de dados saudável

Um Dicionário de dados saudável é aquele em que todos os componentes:

* Estão sendo usados e coletando dados

* Contenha descrições úteis para que os usuários saibam como usá-las

* Estão isentos de duplicatas desnecessárias

* São aprovados pelo administrador

## Verifique a integridade do seu Dicionário de dados

Para identificar problemas de integridade em seu Dicionário de dados:

1. Abra um projeto do Analysis Workspace.

1. Selecione o ícone Dicionário de dados no lado esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em &quot;Acessar o dicionário de dados&quot; em [Visão geral do dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   A janela Dicionário de dados é exibida.

   ![Exibição do administrador do Dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o Conjunto de relatórios correto está selecionado no menu suspenso.

1. No [!UICONTROL **Estado do dicionário**] guia , selecione [!UICONTROL **Exibir**] ao lado de qualquer uma das seguintes opções:

   * [!UICONTROL **componentes estão faltando descrições**]

   * [!UICONTROL **componentes têm duplicatas**]

   * [!UICONTROL **os componentes não têm dados conectados**]

   Dependendo do que você selecionar, o filtro apropriado é aplicado ao Dicionário de dados e somente os componentes relevantes são mostrados.

1. Edite qualquer um dos componentes para melhorar a integridade do Dicionário de dados. Para obter informações sobre como editar um componente no Dicionário de dados, consulte [Editar entradas de componente no Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).