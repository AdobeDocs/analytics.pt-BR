---
title: decodeLinkParameters
description: Ative ou desative as variáveis de rastreamento de link de codificação dupla do AppMeasurement.
exl-id: 7a4cea23-5ae6-4a8b-82a6-c68f9a1f9c49
feature: Variables
source-git-commit: 12d35a0f503ef79eabd55c169d9642c049542798
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 7%

---

# decodeLinkParameters

A variável `decodeLinkParameters` é uma variável do tipo booleano que determina se as variáveis de rastreamento de link são codificadas uma vez (se definidas como `true`) ou duas vezes (se definido como `false`). Isso afeta somente o `linkName` (parte da [`tl()`](../functions/tl-method.md) ) e [`linkURL`](linkurl.md). Ele requer o AppMeasurement v2.24.0 ou superior para ser usado. O valor padrão dessa variável é `false`.

Nas versões do AppMeasurement anteriores à v2.24.0, as variáveis de rastreamento de link sempre estavam codificadas com URL duas vezes. Embora não seja um problema para implementações que normalmente dependem de caracteres de byte único, a codificação dupla criou valores codificados incorretamente para caracteres de vários bytes nos relatórios. Definir essa variável como `true` O codifica os valores de rastreamento de link uma vez, que normalmente é o comportamento desejado.

* Se sua implementação usar caracteres de vários bytes e as variáveis de rastreamento de link forem o URL decodificado para deslocar a codificação dupla do AppMeasurement, defina essa variável como `false`. Esse valor preserva a funcionalidade do AppMeasurement existente.
* Se sua implementação usar caracteres de vários bytes e você não decodificar valores de rastreamento de link de URL, o Adobe recomenda configurar essa variável como `true`.
* Se sua implementação não usar caracteres multibyte, essa variável não será necessária. No entanto, o Adobe recomenda configurar essa variável como `true` nos casos em que caracteres multibyte podem ser enviados.

## Codificação dupla de parâmetros de link usando o SDK da Web

Essa variável é específica do AppMeasurement e não é necessária em nenhum tipo de implementação do SDK da Web.

## Codificação dupla de parâmetros de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.decodeLinkParameters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.decodeLinkParameters` é uma variável do tipo booleano que determina se os valores de rastreamento de link são codificados duas vezes. Se essa variável não estiver definida, o valor padrão será `false` para preservar a funcionalidade de implementações existentes. Adobe recomenda configurar esse valor como `true` para todas as novas implementações, especialmente se você vir valores codificados de URL em relatórios de rastreamento de link.

```js
s.decodeLinkParameters = true;
```
