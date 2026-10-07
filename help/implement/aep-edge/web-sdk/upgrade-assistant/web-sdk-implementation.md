---
title: Implementação do Web SDK no assistente de atualização do Web SDK
description: Revise as ações do Web SDK que o assistente de atualização adiciona às suas regras de tags existentes.
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
source-wordcount: '311'
ht-degree: 0%
---
# Implementação do Web SDK

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Implementação do Web SDK"
>abstract="Revise as ações do Web SDK que o assistente de atualização adiciona às suas regras. As ações do Adobe Analytics permanecem em vigor. Selecione um componente para comparar lado a lado suas configurações atuais e do Web SDK. Somente os componentes enfileirados são adicionados à migração."

<!-- markdownlint-enable MD034 -->

Usando os componentes selecionados e o [mapeamento XDM](xdm-mapping.md), o assistente de atualização adiciona ações do Web SDK às suas regras, diretamente após cada ação do Adobe Analytics. As ações do Analytics permanecem em vigor, portanto, essas regras enviam dados para o Adobe Analytics e para o Web SDK. A maioria dos elementos de dados é transportada sem alterações e as regras continuam fazendo referência a eles pelo nome.

A coluna **[!UICONTROL Tipo de alteração]** mostra o que a finalização da migração faz com cada componente:

* **[!UICONTROL Ações do Web SDK adicionadas]**: o assistente de atualização adiciona ações do Web SDK à regra.
* **[!UICONTROL Sem alteração]**: o componente transporta inalterado.
* **[!UICONTROL Bloqueado]**: o componente precisa de sua revisão para que o assistente de atualização possa adicionar ações do Web SDK a ele. Selecione o componente para ver o que está bloqueando-o.

Selecione um componente para comparar sua configuração atual com a configuração do Web SDK lado a lado. Se você precisar de mais contexto, o assistente de atualização vinculará ao componente na interface do usuário de tags.

Os componentes colocados em fila são adicionados à migração. Para enfileirar um componente, selecione-o na lista ou selecione **[!UICONTROL Enfileirar]** em seus detalhes. Para retirá-lo, selecione **[!UICONTROL Remover da fila]**. O assistente de atualização não altera a propriedade das marcas até que você [finalize a migração](final-review.md#finalize).

O assistente de atualização usa a IA para gerar as ações do Web SDK e os resultados podem não ser precisos ou concluídos. Gerar as ações não verifica como elas se comportam no site; portanto, teste-as antes de publicar a biblioteca.
