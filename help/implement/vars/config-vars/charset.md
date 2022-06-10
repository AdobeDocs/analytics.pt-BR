---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 69%

---

# charSet

A variável charSet é usada pela Adobe para converter dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics. A maioria dos sites não precisa definir essa variável.

Defina essa variável somente se você vir valores ilegíveis ([mojibake](https://pt.wikipedia.org/wiki/Mojibake)) nos relatórios. Essa variável poderá ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no SDK da Web

O SDK da Web suporta atualmente apenas UTF-8 e não fornece opções para alterar a codificação.

## Conjunto de caracteres na extensão Adobe Analytics

O Conjunto de caracteres é um campo sob a variável [!UICONTROL Geral] ao configurar a extensão Adobe Analytics na Coleta de dados do Adobe Experience Platform.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]**, no Adobe Analytics.
1. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Conjunto de caracteres].

É possível usar um conjunto de caracteres predefinido ou especificar um conjunto de caracteres personalizado. Evite alterar o valor de `UTF-8`, a menos que você veja valores ilegíveis nos relatórios.

## s.charSet no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `charSet` é uma cadeia de caracteres. Se você tiver valores ilegíveis no Adobe Analytics, defina essa variável com o mesmo valor que a tag HTML `<meta charset="">` no site.

```js
s.charSet = "UTF-8";
```
