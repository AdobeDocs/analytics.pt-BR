---
description: Os administradores são responsáveis por monitorar a integridade do dicionário de dados. Isso inclui verificar se os componentes estão coletando dados, se estão aprovados, se contêm descrições e estão livres de duplicatas.
title: Monitorar a integridade do dicionário de dados
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 100%

---

# Monitorar a integridade do dicionário de dados {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="Compartilhar componente principal"
>abstract="Quando esta opção estiver selecionada, o componente principal será compartilhado com todos que tiverem acesso aos componentes duplicados (os proprietários e todos com quem os componentes forem compartilhados). Esses usuários podem selecionar o componente principal na lista de componentes para projetos futuros. No entanto, não é possível editar o componente, mesmo que ele seja o proprietário de um componente duplicado que foi consolidado. <br/>Esta opção está disponível somente quando o componente principal é um segmento, uma métrica calculada ou um intervalo de datas. Métricas e dimensões estão sempre disponíveis para todos os usuários.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="Excluir duplicados substituídos"
>abstract="Quando essa opção estiver selecionada, os duplicados consolidados não estarão mais disponíveis para uso. Desmarque essa opção se desejar que os duplicados continuem disponíveis."

<!-- markdownlint-enable MD034 -->

Os administradores do Analytics são responsáveis por manter um dicionário de dados íntegro.

## Características de um dicionário de dados íntegro

Um dicionário de dados íntegro é aquele em que todos os componentes:

* Estão sendo usados e estão coletando dados

* Contêm descrições úteis para que os usuários saibam como usá-los

* Estão isentos de duplicatas desnecessárias

* São aprovados pelo administrador

## Verifique a integridade do seu dicionário de dados

Para identificar problemas de integridade no dicionário de dados:

1. Abra um projeto do Analysis Workspace.

1. Selecione o ícone do dicionário de dados no lado esquerdo do Analysis Workspace. (Maneiras alternativas de acessar o Dicionário de dados são descritas em “Acessar o Dicionário de dados” em [Visão geral do Dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).)

   A janela do dicionário de dados é exibida.

   ![Visualização de administrador do dicionário de dados](assets/data-dictionary-admin.png)

1. Verifique se o conjunto de relatórios correto está selecionado no menu suspenso.

1. Na guia [!UICONTROL **Integridade do dicionário**], selecione [!UICONTROL **Exibir**] ao lado de qualquer uma das seguintes opções:

   * [!UICONTROL **componentes com descrições ausentes**]

   * [!UICONTROL **componentes com duplicatas**]

   * [!UICONTROL **componentes sem dados conectados**]

   Dependendo do que você selecionar, o filtro apropriado é aplicado no dicionário de dados e somente os componentes relevantes são mostrados.

1. Edite qualquer um dos componentes para melhorar a integridade do dicionário de dados. Para obter informações sobre como editar um componente no dicionário de dados, consulte [Editar entradas de componente no dicionário de dados](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).
