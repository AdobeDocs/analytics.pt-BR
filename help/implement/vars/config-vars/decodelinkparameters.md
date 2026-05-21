---
title: decodeLinkParameters
description: Ative ou desative as variáveis de rastreamento de link de codificação dupla do AppMeasurement.
exl-id: 329c521a-b965-4114-93ce-f45f159d4a20
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/YzBsuWvpzof1f8qqJO5j8wuWvHSWdPomxowisPbkg7E
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 310
ht-degree: 8%

---

# decodeLinkParameters

A variável `decodeLinkParameters` é um booliano que determina se as variáveis de rastreamento de link são codificadas uma vez (se definidas como `true`) ou duas vezes (se definidas como `false`). Impacta somente `linkName` (parte do método [`tl()`](../functions/tl-method.md)) e [`linkURL`](linkurl.md). Ele requer o AppMeasurement v2.24.0 ou superior para ser usado. O valor padrão dessa variável é `false`.

Nas versões do AppMeasurement anteriores à v2.24.0, as variáveis de rastreamento de link sempre estavam codificadas com URL duas vezes. Embora não seja um problema para implementações que normalmente dependem de caracteres de byte único, a codificação dupla criou valores codificados incorretamente para caracteres de vários bytes nos relatórios. Configurar essa variável como `true` codifica os valores de rastreamento de link uma vez, que normalmente é o comportamento desejado.

* Se sua implementação usar caracteres de vários bytes e as variáveis de rastreamento de link forem decodificadas por URL para compensar a codificação dupla do AppMeasurement, defina essa variável como `false`. Esse valor preserva a funcionalidade existente do AppMeasurement.
* Se sua implementação usar caracteres de vários bytes e você não decodificar URL dos valores de rastreamento de link, a Adobe recomenda configurar essa variável como `true`.
* Se sua implementação não usar caracteres multibyte, essa variável não será necessária. No entanto, a Adobe recomenda definir essa variável como `true` nos casos em que caracteres multibyte podem ser enviados.

## Codificação dupla de parâmetros de link usando o Web SDK

Essa variável é específica do AppMeasurement e não é necessária em nenhum tipo de implementação do Web SDK.

## Codificação dupla de parâmetros de link usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.decodeLinkParameters no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.decodeLinkParameters` é um booliano que determina se os valores de rastreamento de link são codificados duas vezes. Se essa variável não estiver definida, seu valor padrão será `false` para preservar a funcionalidade para implementações existentes. A Adobe recomenda definir esse valor como `true` para todas as novas implementações, especialmente se você vir valores codificados de URL em relatórios de rastreamento de link.

```js
s.decodeLinkParameters = true;
```
