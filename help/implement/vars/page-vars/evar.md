---
title: eVar
description: Variáveis personalizadas que podem ser usadas na implementação.
translation-type: tm+mt
source-git-commit: f18fbd091333523cd9351bfa461a11f0c3f17bef

---


# eVar

*Esta página de ajuda descreve como implementar eVars. Para obter informações sobre como as eVars funcionam como uma dimensão, consulte[eVars](../../../components/c-variables/dimensionslist/reports-conversion.md)no guia do usuário Componentes.*

As eVars são variáveis personalizadas que podem ser usadas da maneira que você desejar.

> [!TIP] A Adobe recomenda usar eVars em vez de props na maioria dos casos. Em versões anteriores do Adobe Analytics, props e eVars tinham vantagens e desvantagens entre si. No entanto, a Adobe melhorou as eVars de modo que elas atendem a quase todos os casos de uso de props.

Certifique-se de registrar a forma como você usa cada eVar e a lógica delas no [documento de design da solução](../../prepare/solution-design.md).

## Configurar eVars nas configurações do conjunto de relatórios

Antes de usar eVars na implementação, certifique-se de configurar cada eVar nas configurações do conjunto de relatórios. Consulte [Variáveis de conversão](/help/admin/admin/conversion-var-admin/conversion-var-admin.md) no Guia de administração.

## eVars no Adobe Experience Platform Launch

É possível definir eVars ao configurar a extensão do Analytics (variáveis globais) ou em regras.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Go to the [!UICONTROL Rules] tab, then click the desired rule (or create a rule).
4. Em [!UICONTROL Actions], clique em uma [!UICONTROL Adobe Analytics - Set Variables] ação existente ou no ícone &#39;+&#39;.
5. Defina a [!UICONTROL Extension] lista suspensa como Adobe Analytics e [!UICONTROL Action Type] como [!UICONTROL Set Variables].
6. Locate the [!UICONTROL eVars] section.

Você pode selecionar uma eVar para definir um valor ou elemento de dados. Também é possível copiar o valor de outra variável do Analytics.

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

## Vantagens exclusivas de props e eVars

Na versão atual do Adobe Analytics, props e eVars são variáveis personalizadas com recursos semelhantes. No entanto, apresentam várias diferenças importantes:

* Os dados em props estão disponíveis nos relatórios em minutos. As eVars podem levar mais de 30 minutos para serem exibidas nos relatórios.
* As props têm um limite de 100 bytes nos relatórios. As eVars têm um limite de 255 bytes.
* Props podem se tornar propriedades de lista, que aceitam vários valores na mesma ocorrência. Variáveis de lista são variáveis separadas e há apenas três variáveis de lista disponíveis.
* As props, por padrão, não persistem além da ocorrência às quais que estão definidas. As eVars têm expiração personalizada, permitindo determinar quando uma eVar não mais recebe incremento por um evento subsequente. No entanto, se você usar o processamento [de tempo do](../../../components/vrs/vrs-report-time-processing.md)relatório, props e eVars poderão usar um modelo de atribuição personalizado.
