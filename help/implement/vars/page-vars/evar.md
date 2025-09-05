---
title: eVar (variável)
description: Variáveis personalizadas que podem ser usadas na implementação.
feature: Appmeasurement Implementation
exl-id: f89457b2-4186-4276-8637-9992070e3a73
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 92%

---

# eVar

*Esta página de ajuda descreve como implementar eVars. Para obter informações sobre como as eVars funcionam como uma dimensão, consulte [eVars](/help/components/dimensions/evar.md) no guia do usuário Componentes.*

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar. Se você tiver um [documento de design de solução](/help/implement/prepare/solution-design.md), a maioria das dimensões específicas da sua organização acabarão como eVars. Por padrão, as eVars persistem além da ocorrência em que estão definidas. Você pode personalizar a expiração e a alocação em [Variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) nas configurações do conjunto de relatórios.

O número de eVars disponíveis depende do seu contrato com a Adobe. Até 250 eVars estarão disponíveis se seu contrato com a Adobe permitir.

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar eVars na implementação, configure cada eVar nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

## eVars que usam o SDK da Web

As eVars são mapeadas para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm._experience.analytics.customDimensions.eVars.eVar1` a `xdm._experience.analytics.customDimensions.eVars.eVar250`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.eVar1` a `data.__adobe.analytics.eVar250`; ou `data.__adobe.analytics.v1` a `data.__adobe.analytics.v250`

## eVars usando a extensão do Adobe Analytics

É possível definir eVars ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
2. Clique na propriedade de tag desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o [!UICONTROL Tipo de Ação] como [!UICONTROL Definir Variáveis].
6. Localize a seção [!UICONTROL eVars].

Você pode definir uma eVar para um valor ou um elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.eVar1 - s.eVar250 no AppMeasurement e no editor de código personalizado da extensão do Analytics

Cada eVar é uma string que contém valores personalizados específicos para sua organização. O comprimento máximo delas é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de contador

Os valores de eVars normalmente contêm um valor de string. No entanto, você pode configurar eVars para que contenham um contador. Por exemplo, você gostaria de contar o número de pesquisas internas feitas antes de uma compra. Em vez de definir um valor de texto, você usaria a seguinte sintaxe:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Se mais que duas casas decimais forem fornecidas, o contador da eVar é arredondado para duas casas decimais. Um contador eVar não pode conter números negativos.

>[!IMPORTANT]
>
>Primeiro, você deve configurar eVars como &quot;Contador&quot; no Admin Console antes de usar eVars de contador. Consulte [Variáveis de conversão](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-var-admin.md) no Guia de administração.
