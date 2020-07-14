---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 60%

---


# charSet

A variável charSet é usada pela Adobe para converter dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics. A maioria dos sites não precisa definir essa variável.

Defina essa variável somente se você visualizar valores distorcidos ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) nos relatórios. É possível definir essa variável página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no Adobe Experience Platform Launch

O Conjunto de caracteres é um campo da opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Conjunto de caracteres].

É possível usar um conjunto de caracteres predefinido ou especificar um conjunto de caracteres personalizado. Evite alterar o valor a partir de `UTF-8` menos que você veja valores distorcidos em relatórios.

## s.charSet no AppMeasurement e no editor de código personalizado do Launch

A variável `charSet` é uma cadeia de caracteres. Se você tiver valores distorcidos no Adobe Analytics, defina essa variável com o mesmo valor que a tag `<meta charset="">` HTML no seu site.

```js
s.charSet = "UTF-8";
```
