---
title: Revisão final no assistente de atualização do Web SDK
description: Revise e finalize uma migração do Web SDK e publique a biblioteca de tags resultante na produção.
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
source-wordcount: '469'
ht-degree: 0%
---
# Revisão final

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="Revisão final"
>abstract="Selecione a sandbox da Experience Platform a ser usada e revise tudo o que essa migração cria ou altera. Nada é alterado até que você finalize a migração. Quando você o finaliza, o assistente de atualização cria tudo de uma só vez, adiciona as alterações das tags a uma nova biblioteca e torna essa migração somente leitura. Em seguida, você publica essa biblioteca para produção sozinho."

<!-- markdownlint-enable MD034 -->

A revisão final é a última etapa de uma migração. Ela mostra tudo o que a migração cria ou altera no Experience Platform e na propriedade das tags.

## Analisar o que a migração cria {#review}

Primeiro, selecione a sandbox da Experience Platform em que a migração cria seus recursos. Você não pode finalizar a migração até selecionar uma sandbox.

O assistente de atualização lista tudo o que a finalização da migração cria ou altera:

* **[!UICONTROL XDM]**: um novo esquema nomeado após o mapeamento XDM, juntamente com os grupos de campos personalizados necessários. Os grupos de campos padrão já existem, portanto, o esquema os usa como estão. Esta seção aparecerá somente se você optar por criar um novo esquema no [mapeamento XDM](xdm-mapping.md#schema).
* **[!UICONTROL Conjuntos de dados]**: dois conjuntos de dados, um para desenvolvimento e outro para produção. Cada um é nomeado após a migração, como `My migration - Development`.
* **[!UICONTROL Datastreams]**: duas datastreams, uma para desenvolvimento e outra para produção, com o mesmo nome dos conjuntos de dados.
* **[!UICONTROL Marcas do Adobe]**: uma nova biblioteca nomeada após a migração, como `Library - "My migration"`. A biblioteca contém as regras e os elementos de dados alterados pela migração, juntamente com a configuração de extensão de que as ações do Web SDK precisam.

## Finalizar a migração {#finalize}

Até que você finalize a migração, o assistente de atualização não alterará a propriedade das tags nem criará nada no Experience Platform.

>[!IMPORTANT]
>
>Depois de finalizar uma migração, ela se torna somente leitura. Você ainda pode abri-lo na página **[!UICONTROL Migrações]** para ver o que ele criou, mas não pode alterá-lo nem finalizá-lo novamente. Como a nova biblioteca ainda está em desenvolvimento, você pode editar ou remover as alterações de tags na interface do usuário de tags antes de publicar a biblioteca.

1. Selecione **[!UICONTROL Criar artefatos]**.
1. Na caixa de diálogo **[!UICONTROL Verificar estas recomendações]**, selecione **[!UICONTROL Continuar]**.
1. Em **[!UICONTROL Finalizar esta migração?]** , selecione **[!UICONTROL Finalizar]**.

O assistente de atualização cria tudo de uma só vez e mostra o progresso. Ele adiciona as alterações de tags à nova biblioteca, mas não a publica.

## Publicar suas alterações {#publish}

Depois de finalizar a migração, mova a nova biblioteca pelo fluxo de publicação de tags:

1. Crie e teste a biblioteca em seu ambiente de desenvolvimento para garantir que a implementação do Web SDK envie os dados esperados.
1. Envie a biblioteca para aprovação e teste-a no ambiente de preparo.
1. Aprove a biblioteca e publique-a na produção.

Consulte [Fluxo de publicação](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow) no guia do usuário de marcas.
