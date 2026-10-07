---
title: Gerenciar migrações no assistente de atualização do Web SDK
description: Crie, exiba e abra migrações no assistente de atualização do Web SDK.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 0%
---
# Gerenciar migrações

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="Migrações"
>abstract="Cada migração atualiza a implementação do Adobe Analytics em uma propriedade de tags para a Web SDK. Abra uma migração para continuar de onde parou ou selecione &#39;Novo&#39; para iniciar uma migração."

A página **[!UICONTROL Migrações]** é o ponto de partida para o assistente de atualização do Web SDK. Ela lista as migrações na sua organização, incluindo o progresso, o status e quem as criou. Use esta página para criar uma migração ou abrir uma existente.

## Criar uma migração {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="Nova migração"
>abstract="Selecione a propriedade das tags que você deseja migrar e uma biblioteca nessa propriedade. O assistente de atualização tira um instantâneo da biblioteca ao criar a migração. As alterações feitas na biblioteca após um instantâneo de migração não são incluídas. A propriedade das tags não é alterada até que você finalize a migração."

<!-- markdownlint-enable MD034 -->

Antes de criar uma migração, verifique se você atende aos [pré-requisitos](overview.md#prerequisites).

1. Na página **[!UICONTROL Migrações]**, selecione **[!UICONTROL Novo]**.
1. Insira um nome para a migração e, opcionalmente, uma descrição.
1. Selecione a propriedade das tags que você deseja migrar.
1. Selecione uma biblioteca de tags. Ao criar a migração, o assistente de atualização captura um instantâneo da implementação como ela existe nesta biblioteca. As alterações feitas na biblioteca depois disso não serão refletidas na migração.
1. Selecione **[!UICONTROL Criar]**.

A nova migração é exibida na lista. Abra para iniciar a [seleção de componente](component-selection.md).

## Abrir uma migração {#open}

Selecione o nome de uma migração para abri-la. As etapas da migração são exibidas na navegação à esquerda. Você pode retornar a qualquer etapa concluída para revisá-la ou alterá-la sempre que desejar, mas as etapas que você ainda não atingiu ainda não estão disponíveis.

O assistente de atualização salva o progresso à medida que você percorre as etapas, para que seja possível sair de uma migração e retornar a ela posteriormente. Nada configurado entrará em vigor até que você [finalize a migração](final-review.md#finalize). Depois de finalizar, a migração se torna somente leitura. Você ainda pode abri-lo para ver o que ele criou, mas não pode alterá-lo.

## Outras ações de migração {#actions}

Selecione uma linha de migração para mostrar as ações disponíveis para ela:

* **[!UICONTROL Continuar]**: abre a migração.
* **[!UICONTROL Execução de duplicação]**: cria uma cópia da migração.
* **[!UICONTROL Renomear]**: altera o nome e a descrição da migração.
* **[!UICONTROL Arquivar]**: altera o status da migração para **[!UICONTROL Arquivada]**.
* **[!UICONTROL Excluir migração]**: exclui permanentemente a migração. Você não pode desfazer isso.
