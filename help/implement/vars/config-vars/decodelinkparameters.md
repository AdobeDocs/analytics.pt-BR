---
title: decodeLinkParameters
description: Ative ou desative as variáveis de rastreamento de link de codificação dupla do AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Variables
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 8%

---

# decodeLinkParameters

A variável `decodeLinkParameters` é um booliano que determina se as variáveis de rastreamento de link são codificadas uma vez (se definidas como `true`) ou duas vezes (se definidas como `false`). Impacta somente `linkName` (parte do método [`tl()`](../functions/tl-method.md)) e [`linkURL`](linkurl.md). Ele requer o AppMeasurement v2.24.0 ou superior para ser usado. O valor padrão dessa variável é `false`.

Nas versões do AppMeasurement anteriores à v2.24.0, as variáveis de rastreamento de link sempre estavam codificadas com URL duas vezes. Embora não seja um problema para implementações que normalmente dependem de caracteres de byte único, a codificação dupla criou valores codificados incorretamente para caracteres de vários bytes nos relatórios. Configurar essa variável como `true` codifica os valores de rastreamento de link uma vez, que normalmente é o comportamento desejado.

* Se sua implementação usar caracteres multibyte e as variáveis de rastreamento de link forem decodificadas por URL para a codificação dupla do AppMeasurement offset, defina essa variável como `false`. Esse valor preserva a funcionalidade do AppMeasurement existente.
* Se sua implementação usar caracteres de vários bytes e você não decodificar URL dos valores de rastreamento de link, o Adobe recomenda configurar essa variável como `true`.
* Se sua implementação não usar caracteres multibyte, essa variável não será necessária. No entanto, o Adobe recomenda definir essa variável como `true` nos casos em que caracteres multibyte podem ser enviados.

## Codificação dupla de parâmetros de link usando o SDK da Web

Essa variável é específica do AppMeasurement e não é necessária em nenhum tipo de implementação do SDK da Web.

## Codificação dupla de parâmetros de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.decodeLinkParameters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.decodeLinkParameters` é um booliano que determina se os valores de rastreamento de link são codificados duas vezes. Se essa variável não estiver definida, seu valor padrão será `false` para preservar a funcionalidade para implementações existentes. A Adobe recomenda definir esse valor como `true` para todas as novas implementações, especialmente se você vir valores codificados de URL em relatórios de rastreamento de link.

```js
s.decodeLinkParameters = true;
```
