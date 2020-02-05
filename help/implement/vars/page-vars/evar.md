---
title: eVar
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: tm+mt
source-git-commit: dcb69257fd29686ae346cf4d0cf50ed041ebcbbc

---


# eVar

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar.

> [!TIP] A Adobe recomenda usar eVars em props na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars para onde elas atendem a quase todos os casos de uso de props.

Certifique-se de registrar como você usa cada eVar e sua lógica no documento [de design da](../../prepare/solution-design.md)solução.

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar eVars na implementação, certifique-se de configurar cada eVar nas configurações do conjunto de relatórios. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## eVars no Adobe Experience Platform Launch

É possível definir eVars ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
4. Em [!UICONTROL Ações], clique em uma ação [!UICONTROL Adobe Analytics - Definir variáveis] ou clique no ícone &#39;+&#39;.
5. Defina a lista suspensa [!UICONTROL Extensão] como Adobe Analytics e o Tipo [!UICONTROL de] ação como [!UICONTROL Definir variáveis].
6. Localize a seção [!UICONTROL eVars] .

Você pode selecionar uma eVar para definir um valor ou elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

## s.eVar1 - s.eVar250 no editor de código personalizado do AppMeasurement e Launch

Cada eVar é uma string que contém valores personalizados específicos para sua organização. Seu comprimento máximo é de 255 bytes; valores com mais de 255 bytes são truncados automaticamente quando enviados para a Adobe.

```js
s.eVar1 = "Example custom value";
```

## eVars de contador

Os valores de eVar normalmente contêm um valor de string. No entanto, você pode configurar eVars para que contenham um contador. Por exemplo, você gostaria de contar o número de pesquisas internas feitas antes de uma compra. Em vez de definir um valor de texto, você usaria a seguinte sintaxe:

```js
// Increment a counter eVar by 1
s.eVar1 = "+1";

// Increment a counter eVar by 12.49
s.eVar1 = "+12.49";
```

Se mais que duas casas decimais forem fornecidas, o contador da eVar é arredondado por duas casas decimais. Um contador eVar não pode conter números negativos.

> [!IMPORTANT] Primeiro, você deve configurar eVars como &quot;Contador&quot; no Admin Console antes de usar eVars de contador. See [Conversion variables](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) in the Admin guide.

## Vantagens exclusivas para props ou eVars

Na versão atual do Adobe Analytics, props e eVars são variáveis personalizadas com recursos semelhantes. No entanto, apresentam várias diferenças importantes:

* Os dados em props estão disponíveis em relatórios em minutos. As eVars podem levar mais de 30 minutos para serem exibidas nos relatórios.
* As props têm um limite de 100 bytes nos relatórios. As eVars têm um limite de 255 bytes.
* As props podem se tornar propriedades de lista, que aceitam vários valores na mesma ocorrência. List vars são uma variável separada e há apenas três variáveis de lista disponíveis.
* As props por padrão não persistem além da ocorrência que estão definidas. As eVars têm expiração personalizada, permitindo determinar quando uma eVar não recebe mais crédito por um evento subsequente. No entanto, se você usar o processamento [de tempo do](../../../components/vrs/vrs-report-time-processing.md)relatório, props e eVars poderão usar um modelo de atribuição personalizado.
