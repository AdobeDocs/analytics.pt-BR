---
title: Mapeamento XDM no assistente de atualização do Web SDK
description: Mapeie suas variáveis do Adobe Analytics para campos em um esquema XDM como parte de uma migração do Web SDK.
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
source-wordcount: '419'
ht-degree: 3%
---
# Mapeamento XDM

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="Mapeamento XDM"
>abstract="Mapeie as variáveis do Analytics selecionadas para campos em um esquema XDM. O assistente de atualização pode criar um novo esquema com mapeamentos sugeridos por IA ou mapear variáveis para um esquema que você já tem. Revise todos os mapeamentos antes de continuar."

<!-- markdownlint-enable MD034 -->

O Web SDK envia dados usando [campos do Experience Data Model (XDM)](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/home), para que cada variável do Analytics transportada da [verificação do conjunto de relatórios](rs-verification.md) precise de um campo correspondente em um esquema XDM. Nesta etapa, escolha um esquema e mapeie as variáveis aos campos.

## Escolher um esquema {#schema}

Você pode criar o mapeamento de uma das duas formas a seguir:

* **Criar um novo esquema**: o assistente de atualização analisa suas variáveis do Analytics e sugere um campo XDM para cada uma e, em seguida, gera um esquema dessas sugestões para você revisar.
* **Usar um esquema existente**: selecione um esquema que já existe no Experience Platform e mapeie cada variável para um campo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="Preferência de grupo de campos"
>abstract="Escolha que tipo de grupo de campos o assistente de atualização deve considerar ao criar seu esquema. Os grupos de campos padrão são definidos pela Adobe. Os grupos de campos personalizados são definidos pela sua organização."

<!-- markdownlint-enable MD034 -->

Ao criar um novo esquema, você também escolhe se o assistente de atualização favorece grupos de campos padrão ou personalizados. Os grupos de campos padrão são definidos pela Adobe, enquanto os grupos de campos personalizados são definidos pela organização. Consulte [Grupo de campos](https://experienceleague.adobe.com/pt-br/docs/experience-platform/xdm/schema/composition#field-group) na documentação do XDM.

## Revisar o mapeamento {#review}

O mapeamento lista cada variável do Analytics junto com o campo XDM para o qual ele é mapeado, com uma visualização do esquema completo ao lado dele. Selecione parte do schema para filtrar a lista para as variáveis que mapeiam para ele. Você pode ajustar os mapeamentos individuais e o próprio esquema.

O assistente de atualização usa IA para sugerir mapeamentos e os resultados podem não ser precisos ou completos. Revise todos os mapeamentos antes de continuar. O assistente de atualização não cria o esquema no Experience Platform até que você [finalize a migração](final-review.md#finalize).

Quando terminar, selecione **[!UICONTROL Salvar e continue]** para salvar seu mapeamento e ir para a [implementação do Web SDK](web-sdk-implementation.md). Para alterar o mapeamento depois de salvá-lo, selecione **[!UICONTROL Editar]**, faça suas alterações e selecione **[!UICONTROL Salvar e continuar]** novamente. As alterações que você não salvar dessa maneira não serão incluídas ao finalizar a migração.
