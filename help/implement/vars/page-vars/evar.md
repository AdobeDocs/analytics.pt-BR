---
title: eVar
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: tm+mt
source-git-commit: 10e157e370367374b55ee9c87c0e5c7ca9e99c1a
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 68%

---


# eVar

*Esta página de ajuda descreve como implementar eVars. Para obter informações sobre como as eVars funcionam como uma dimensão, consulte[eVars](/help/components/dimensions/evar.md)no guia do usuário Componentes.*

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar. Se você tiver um documento [de design de](/help/implement/prepare/solution-design.md)solução, a maioria das dimensões específicas da sua organização acabarão como eVars. Por padrão, as eVars persistem além da ocorrência em que estão definidas. Você pode personalizar a expiração e a alocação em Variáveis [de](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) conversão nas configurações do conjunto de relatórios.

O número de eVars disponíveis depende de seu contrato com a Adobe. Até 250 eVars estarão disponíveis se seu contrato com a Adobe oferecer suporte para isso.

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar eVars na implementação, certifique-se de configurar cada eVar nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

## eVars no Adobe Experience Platform Launch

É possível definir eVars ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone “+”.
5. Selecione Adobe Analytics na lista suspensa [!UICONTROL Extensão] e defina [!UICONTROL Tipo de ação] como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL eVars].

É possível definir uma eVar como um valor ou elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.eVar1 e s.eVar250 no AppMeasurement e no editor de código personalizado do Launch

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

> [!IMPORTANT] Primeiro, você deve configurar eVars como &quot;Contador&quot; no Admin Console antes de usar eVars de contador. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração.
