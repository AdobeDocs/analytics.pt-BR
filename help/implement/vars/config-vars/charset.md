---
title: charSet
description: A variável charSet determina qual codificação a Adobe usa para analisar a solicitação de imagem.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '196'
ht-degree: 100%

---

# charSet

A variável charSet é usada pela Adobe para converter dados recebidos em UTF-8 para armazenamento e relatório pelo Analytics. A maioria dos sites não precisa definir essa variável.

Defina essa variável somente se você vir valores ilegíveis ([mojibake](https://pt.wikipedia.org/wiki/Mojibake)) nos relatórios. Essa variável poderá ser definida página por página se o site usar codificações diferentes em páginas diferentes.

## Conjunto de caracteres no Adobe Experience Platform Launch

O Conjunto de caracteres é um campo da opção [!UICONTROL Geral] ao configurar a extensão do Adobe Analytics.

1. Faça logon em [launch.adobe.com](https://launch.adobe.com) usando as credenciais da Adobe ID.
2. Clique na propriedade desejada.
3. Vá até a guia [!UICONTROL Extensões] e clique no botão [!UICONTROL Configurar], no Adobe Analytics.
4. Expanda a opção [!UICONTROL Geral], que revela o campo [!UICONTROL Conjunto de caracteres].

É possível usar um conjunto de caracteres predefinido ou especificar um conjunto de caracteres personalizado. Evite alterar o valor de `UTF-8`, a menos que você veja valores ilegíveis nos relatórios.

## s.charSet no AppMeasurement e no editor de código personalizado do Launch

A variável `charSet` é uma cadeia de caracteres. Se você tiver valores ilegíveis no Adobe Analytics, defina essa variável com o mesmo valor que a tag HTML `<meta charset="">` no site.

```js
s.charSet = "UTF-8";
```
