---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar sua solicitação de imagem.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

A variável charSet é usada pela Adobe para converter dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics. Se o site usar um charSet diferente de UTF-8, essa variável permitirá que seus dados sejam corretamente codificados pela Adobe. Essa variável pode ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no Adobe Experience Platform Launch

Conjunto de caracteres é um campo sob o [!UICONTROL procedimento Geral] ao configurar a extensão do Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar] em Adobe Analytics.
4. Expanda o acordeão [!UICONTROL Geral] , que revela o campo Conjunto de [!UICONTROL caracteres] .

Você pode usar um conjunto de caracteres predefinido ou um conjunto de caracteres personalizado. Esse valor deve corresponder à codificação de caracteres do site. A maioria dos sites usa `UTF-8`.

## s.charSet no AppMeasurement e Iniciar editor de código personalizado

A `charSet` variável é uma string. Defina essa variável com o mesmo valor que a tag `<meta charset="">` HTML do site.

```js
s.charSet = "UTF-8";
```
