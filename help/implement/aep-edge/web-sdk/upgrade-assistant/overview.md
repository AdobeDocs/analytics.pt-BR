---
title: Assistente de atualização do Web SDK
description: Planeje e execute a migração da sua extensão de tags do Adobe Analytics para o Adobe Experience Platform Web SDK.
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
source-wordcount: '535'
ht-degree: 3%
---
# Assistente de atualização do Web SDK

O assistente de atualização do Web SDK ajuda a planejar e executar a migração da extensão de tags da Adobe Analytics para o Adobe Experience Platform Web SDK. Ela leva a migração para um único espaço de trabalho guiado, para que você possa migrar da implementação de tags existente para a Web SDK de forma estruturada e rastreável.

## Funcionamento do assistente de atualização {#how-it-works}

Cada migração funciona com a implementação do Adobe Analytics em uma propriedade de tags. O assistente de atualização adiciona ações do Web SDK às regras existentes sem remover as ações do Adobe Analytics. Portanto, a implementação continua enviando dados para o Adobe Analytics com o Web SDK.

O assistente de atualização converte somente componentes do Adobe Analytics. É possível incluir componentes de outras extensões, como Adobe Target, Adobe Audience Manager ou extensões de terceiros, mas o assistente de atualização não os converte para o Web SDK.

O assistente de atualização orientará você pelas etapas a seguir e cada etapa se baseará nas decisões tomadas na anterior:

1. **[Seleção de componentes](component-selection.md)**: escolha as regras, os elementos de dados e as extensões a serem incluídos na migração.
1. **[Conclusões de auditoria](audit-findings.md)**: revise as recomendações de limpeza opcionais para os componentes selecionados.
1. **[Verificação do conjunto de relatórios](rs-verification.md)**: revise as variáveis do Analytics em seus conjuntos de relatórios e escolha quais serão postergadas.
1. **[Mapeamento XDM](xdm-mapping.md)**: mapeie as variáveis do Analytics para campos em um esquema XDM.
1. **[Implementação do Web SDK](web-sdk-implementation.md)**: revise as ações do Web SDK que o assistente de atualização adiciona às suas regras.
1. **[Revisão final](final-review.md)**: selecione uma sandbox da Experience Platform, analise o que a migração cria e finalize a migração.

Cada etapa configura parte da migração e você pode voltar às etapas concluídas para revisá-las ou alterá-las sempre que desejar. O assistente de atualização não altera a propriedade das tags ou cria nada no Experience Platform até que você finalize a migração. Quando você o finaliza, o assistente de atualização cria tudo de uma vez e adiciona as alterações das tags a uma nova biblioteca. Em seguida, você testa essa biblioteca e a publica na produção usando o fluxo de publicação de tags.

>[!IMPORTANT]
>
>O assistente de atualização usa a inteligência artificial (AI) para gerar recomendações, como mapeamentos de campo XDM e configurações de regras do Web SDK. Essas recomendações podem não ser precisas ou completas. Verifique-as antes de publicar suas alterações na produção.

## Pré-requisitos {#prerequisites}

Antes de criar uma migração, verifique se você tem:

* As [permissões](#permissions) que o assistente de atualização requer.
* Uma propriedade de tags que usa a extensão Adobe Analytics.
* Uma biblioteca nessa propriedade que contém a implementação que você deseja migrar. A biblioteca pode estar em qualquer estado, incluindo publicada. Consulte [Bibliotecas](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries) no guia do usuário de marcas.

### Permissões {#permissions}

O assistente de atualização requer o seguinte acesso. Trabalhe com o administrador de produtos do Experience Platform da sua organização para obter as permissões que você não tem.

| Tipo de acesso | Obrigatório |
| --- | --- |
| [Permissões da Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL Visualizar esquemas]</li><li>[!UICONTROL Gerenciar esquemas]</li><li>[!UICONTROL Visualizar conjuntos de dados]</li><li>[!UICONTROL Gerenciar conjuntos de dados]</li><li>[!UICONTROL Exibir namespaces de identidade]</li></ul> |
| Acesso ao produto | <ul><li>Coleção de dados (tags)</li><li>Adobe Analytics</li></ul> |
| [Direitos de marcas](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL Gerenciar propriedades] |

Quando estiver pronto, [crie uma migração](manager.md#create).
