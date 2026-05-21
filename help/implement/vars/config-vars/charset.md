---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
TQID: https://experienceleague.adobe.com/bPK-uLu-IgKnJWGpAUnS7cmRm808jhetzm-Cyd2R39o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 235
ht-degree: 66%

---

# charSet

A variável `charSet` é usada pelo Adobe para converter dados recebidos em UTF-8 para armazenamento e relatórios do Analytics. A maioria dos sites não precisa definir essa variável.

Defina essa variável somente se você vir valores ilegíveis ([mojibake](https://pt.wikipedia.org/wiki/Mojibake)) nos relatórios. Essa variável poderá ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no Web SDK

Atualmente, o Web SDK oferece suporte apenas a UTF-8 e não fornece opções para alterar a codificação.

## Conjunto de caracteres na extensão do Adobe Analytics

O Conjunto de caracteres é um campo da opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics na Coleção de dados da Adobe Experience Platform.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Conjunto de caracteres].

É possível usar um conjunto de caracteres predefinido ou especificar um conjunto de caracteres personalizado. Evite alterar o valor de `UTF-8`, a menos que você veja valores ilegíveis nos relatórios.

## s.charSet no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `charSet` é uma cadeia de caracteres. Se você tiver valores ilegíveis no Adobe Analytics, defina essa variável com o mesmo valor que a tag HTML `<meta charset="">` no site.

```js
s.charSet = "UTF-8";
```
