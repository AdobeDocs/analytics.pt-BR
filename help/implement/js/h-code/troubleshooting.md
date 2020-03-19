---
title: Solução de problemas de implementações do Código H
description: Saiba mais sobre alguns problemas comuns com implementações JavaScript herdadas.
translation-type: ht
source-git-commit: 69138bdedb42b66449426fee39822520ee4b1198

---


# Solução de problemas de implementações do Código H

Veja a seguir as etapas de solução de problemas específicas das implementações do Código H.

## Inserção do código do Analytics na marca do cabeçalho

> [!NOTE] Embora as implementações do Código H exijam a referência ao código na tag `<body>`, outras implementações (como o uso do Adobe Experience Platform Launch) exigem a referência do código na tag `<head>`.

O código do Analytics cria uma imagem invisível de 1x1 pixels. Anteriormente, uma prática comum de implementação era colocar a referência `s_code.js` na `<head>` tag. Colocar o código aqui impedia que a imagem afetasse o layout da página de qualquer forma. Além disso, ele é executado antes, permitindo a contagem de exibições de página para carregamentos parciais de página com mais eficiência.

No entanto, determinados elementos do código exigem a existência do objeto `<body>`. Se o código JavaScript do Analytics estiver na tag `<head>`, ele será executado antes que o objeto `<body>` exista. Como resultado, sua implementação não coletará os dados do [!UICONTROL ClickMap], o rastreamento automático dos downloads de arquivo ou links de saída ou dados de tipo de conexão. Inserir a referência de script `s_code.js` na tag `<head>` funciona, mas o resultado é uma versão muito limitada do Analytics.

O código do Analytics pode ser inserido em qualquer lugar dentro da tag `<body>` de uma página HTML bem formada. A Adobe recomenda colocar o código do Analytics o mais próximo possível da parte superior da tag `<body>`. Verifique se todas as variáveis de página estão definidas após o carregamento do arquivo `s_code.js`.

> [!TIP] Se quiser integrar o Adobe Analytics ao Adobe Target, o arquivo de inclusão do JavaScript deverá ser colocado na parte inferior da página.
