---
title: doubleEncodeLinkParameters
description: Ative ou desative as variáveis de rastreamento de link de codificação dupla do AppMeasurement.
source-git-commit: d0e3b28590b24d630a192ee857a7d84c115dc8c1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# doubleEncodeLinkParameters

A variável `doubleEncodeLinkParameters` é uma variável do tipo booleano que determina se as variáveis de rastreamento de link são codificadas uma vez (se definidas como `false`) ou duas vezes (se definido como `true`). Isso afeta somente o `linkName` (parte da [`tl()`](../functions/tl-method.md) ) e [`linkURL`](linkurl.md). Ele requer o AppMeasurement 2.23.1 ou superior para ser usado. O valor padrão dessa variável é `true`.

Em versões anteriores do AppMeasurement, as variáveis de rastreamento de link sempre estavam codificadas com URL duas vezes. Embora não seja um problema para implementações que normalmente dependem de caracteres de byte único, a codificação dupla criou valores codificados incorretamente para caracteres de vários bytes nos relatórios. Definir essa variável como `false` O codifica os valores de rastreamento de link uma vez, que normalmente é o comportamento desejado.

* Se sua implementação usar caracteres de vários bytes e as variáveis de rastreamento de link forem o URL decodificado para deslocar a codificação dupla do AppMeasurement, defina essa variável como `true`. Esse valor preserva a funcionalidade do AppMeasurement existente.
* Se sua implementação usar caracteres de vários bytes e você não decodificar valores de rastreamento de link de URL, o Adobe recomenda configurar essa variável como `false`.
* Se sua implementação não usar caracteres multibyte, essa variável não será necessária. No entanto, o Adobe recomenda configurar essa variável como `false` nos casos em que caracteres multibyte podem ser enviados.

## Codificação dupla de parâmetros de link usando o SDK da Web

Essa variável é específica do AppMeasurement e não é necessária em nenhum tipo de implementação do SDK da Web.

## Codificação dupla de parâmetros de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.doubleEncodeLinkParameters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.doubleEncodeLinkParameters` é uma variável do tipo booleano que determina se os valores de rastreamento de link são codificados duas vezes. Se essa variável não estiver definida, o valor padrão será `true` para preservar a funcionalidade de implementações existentes. Adobe recomenda configurar esse valor como `false` para todas as novas implementações, especialmente se você vir valores codificados de URL em relatórios de rastreamento de link.

```js
s.doubleEncodeLinkParameters = false;
```
