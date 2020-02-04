---
title: Solução de problemas de implementações do código H
description: Aprenda alguns problemas comuns com implementações JavaScript herdadas.
translation-type: tm+mt
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Solução de problemas de implementações do código H

Veja a seguir as etapas de solução de problemas específicas das implementações do código H.

## Inserção do código do Analytics na marca do cabeçalho

> [!NOTE] Embora as implementações do Código H exijam a referência do código na `<body>` tag , outras implementações (como o uso do Adobe Experience Platform Launch) exigem a referência do código na `<head>` tag .

O código do Analytics cria uma imagem invisível de 1x1 pixels. Anteriormente, uma prática comum de implementação era colocar a `s_code.js` referência na `<head>` tag . Colocar o código aqui impedia que a imagem afetasse o layout da página de qualquer forma. Ele também é executado mais cedo, o que permite contar exibições de página para cargas parciais de página com mais eficiência.

However, certain elements of the code require the existence of the `<body>` object. Se o código JavaScript do Analytics estiver na `<head>` tag, ele será executado antes que o `<body>` objeto exista. As a result, your implementation does not collect [!UICONTROL ClickMap] data, automatic tracking of file downloads or exit links, or connection type data. Inserir a referência de script `s_code.js` na `<head>` tag funciona, mas o resultado é uma versão muito limitada do Analytics.

The Analytics code can be placed anywhere inside the `<body>` tag of a well-formed HTML page. A Adobe recomenda colocar o código do Analytics o mais próximo possível da parte superior da `<body>` tag. Verifique se todas as variáveis de página estão definidas após o carregamento do `s_code.js` arquivo.

> [!TIP] Se você quiser integrar o Adobe Analytics ao Adobe Target, o arquivo de inclusão do JavaScript deverá ser colocado na parte inferior da página.
