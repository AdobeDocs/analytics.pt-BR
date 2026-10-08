---
title: Conclusões de auditoria no assistente de atualização do Web SDK
description: Revise e resolva as recomendações de limpeza opcionais para seus componentes de tags antes de migrar para o Web SDK.
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 2%
---
# Conclusões da auditoria

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="Conclusões da auditoria"
>abstract="As descobertas apontam regras e elementos de dados que você pode querer limpar antes de migrar, como elementos de dados que nada faz referência. Aceite uma conclusão para incluir sua alteração recomendada na migração ou recuse-a para deixar o componente como está. Esta etapa é opcional."

<!-- markdownlint-enable MD034 -->

O assistente de atualização verifica as regras e os elementos de dados selecionados na [seleção de componentes](component-selection.md) e sinaliza aqueles que você deseja limpar antes de migrar:

* Regras duplicadas, ou regras que compartilham eventos e condições, que você pode consolidar
* Sequências de ação da regra que podem afetar a precisão dos dados
* Elementos de dados duplicados que podem ser consolidados
* Elementos de dados que podem não ser usados, que podem ser desativados

Esta etapa é opcional. Você pode resolver quantos achados quiser ou continuar diretamente para [Preparação do mapeador](mapper-prep.md).

## Revisar uma conclusão {#review}

Selecione uma descoberta para ver seus detalhes, incluindo:

* Uma descrição da conclusão
* A configuração atual do componente
* Onde o componente é usado, tanto na propriedade das tags quanto no Adobe Analytics

Cada descoberta inclui uma ação recomendada, que depende do tipo de descoberta. Por exemplo, a ação recomendada para um elemento de dados que nada menciona é desativá-lo.

>[!IMPORTANT]
>
>Um elemento de dados sinalizado como não usado ainda pode ser referenciado dinamicamente ou de fora das tags. Antes de aceitar uma conclusão, verifique as alterações propostas, o código personalizado, a ordem de ação e as referências para confirmar se elas mantêm o comportamento pretendido.

## Resolver descobertas {#resolve}

Quando você executa a ação recomendada de uma descoberta, ela é aceita. O assistente de atualização adiciona a alteração à migração e a aplica quando você [finaliza a migração](final-review.md#finalize). Se você não quiser fazer a alteração, recuse a conclusão.

Você pode reabrir uma descoberta aceita ou recusada se mudar de ideia. Para atualizar várias descobertas de uma só vez, selecione-as na lista.
