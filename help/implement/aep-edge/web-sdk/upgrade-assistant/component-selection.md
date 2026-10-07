---
title: Seleção de componentes no assistente de atualização do Web SDK
description: Escolha quais regras de tags, elementos de dados e extensões serão incluídos em uma migração do Web SDK.
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
source-wordcount: '401'
ht-degree: 0%
---
# Seleção de componente

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="Seleção de componente"
>abstract="Escolha as regras, os elementos de dados e as extensões a serem incluídos nesta migração. Os componentes que contribuem ativamente para a implementação do Adobe Analytics são selecionados por padrão. As etapas posteriores só funcionam com os componentes selecionados aqui."

A seleção de componentes é a primeira etapa de uma migração. Use-a para escolher quais regras, elementos de dados e extensões da propriedade de tags serão incluídos na migração.

O assistente de atualização organiza os componentes da propriedade de marcas nas guias **[!UICONTROL Regras]**, **[!UICONTROL Elementos de Dados]** e **[!UICONTROL Extensões]**. Cada guia lista todos os componentes desse tipo da propriedade, com base no instantâneo da biblioteca que o assistente de atualização fez quando você [criou a migração](manager.md#create). Por padrão, somente os componentes que contribuem ativamente para a implementação do Adobe Analytics são selecionados. Você pode selecionar ou limpar qualquer componente.

A coluna **[!UICONTROL Publicado]** mostra se cada componente faz parte da biblioteca selecionada. Os componentes que não fazem parte da biblioteca existem na propriedade de tags, mas não nessa biblioteca. Para filtrar a lista por este item, use o filtro **[!UICONTROL Source]**.

É possível incluir componentes que não estão relacionados ao Adobe Analytics, como componentes para Adobe Target, Adobe Audience Manager ou extensões de terceiros, mas o assistente de atualização não os converte para o Web SDK.

Os componentes selecionados determinam com quais etapas posteriores você trabalhará. Por exemplo, você pode incluir elementos de dados que nada faz referência, de modo que [conclusões de auditoria](audit-findings.md) possam sinalizá-los para limpeza.

## Exibir detalhes do componente {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="Uso de tags"
>abstract="As regras, os elementos de dados e as extensões que usam esse componente. O uso da extensão abrange apenas as configurações da extensão. O uso dentro de uma regra é exibido em Uso da regra."

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Uso do Analytics"
>abstract="As variáveis do Adobe Analytics às quais esse componente está atribuído, agrupadas por tipo de variável."

<!-- markdownlint-enable MD034 -->

Selecione o nome de um componente para abrir um painel que mostra sua configuração e onde ele é usado:

* **[!UICONTROL Uso de tags]**: as regras, os elementos de dados e as extensões que usam o componente. **[!UICONTROL Uso de extensão]** abrange somente as configurações de extensão. O uso dentro de uma regra aparece em **[!UICONTROL Uso da regra]**.
* **[!UICONTROL Uso do Analytics]**: as variáveis do Adobe Analytics às quais o componente está atribuído, agrupadas por tipo de variável.

Para ver o componente na interface das tags, selecione o nome dele na parte superior do painel.

Quando terminar, selecione **[!UICONTROL Salvar e continuar]** para acessar [descobertas de auditoria](audit-findings.md).