---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
translation-type: ht
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

A variável charSet é usada pela Adobe para converter dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics. Se o site usar um charSet diferente de UTF-8, essa variável permitirá que os dados sejam codificados corretamente pela Adobe. Essa variável pode ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no Adobe Experience Platform Launch

O Conjunto de caracteres é um campo da opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Conjunto de caracteres].

É possível usar um conjunto de caracteres predefinido ou especificar um conjunto de caracteres personalizado. Esse valor deve corresponder à codificação de caracteres do site. A maioria dos sites usa `UTF-8`.

## s.charSet no AppMeasurement e no editor de código personalizado do Launch

A variável `charSet` é uma cadeia de caracteres. Defina essa variável com o mesmo valor que a tag HTML `<meta charset="">` do site.

```js
s.charSet = "UTF-8";
```
