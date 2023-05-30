---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: ef82c34f97a0c8172f097b83b521860a1897c82c
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 66%

---

# charSet

A variável `charSet` é usada pelo Adobe para converter dados recebidos em UTF-8 para armazenamento e relatórios do Analytics. A maioria dos sites não precisa definir essa variável.

Defina essa variável somente se você vir valores ilegíveis ([mojibake](https://pt.wikipedia.org/wiki/Mojibake)) nos relatórios. Essa variável poderá ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no SDK da Web

Atualmente, o SDK da Web é compatível apenas com UTF-8 e não fornece opções para alterar a codificação.

## Conjunto de caracteres na extensão do Adobe Analytics

O Conjunto de caracteres é um campo sob a [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics na Coleção de dados da Adobe Experience Platform.

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
