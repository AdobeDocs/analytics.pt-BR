---
title: Solução de problemas de implementações do Código H
description: Saiba mais sobre alguns problemas comuns com implementações JavaScript herdadas.
feature: Implementation Basics
exl-id: 51d6e286-7008-4736-a196-bd8ac4e3e9cb
role: Developer
TQID: https://experienceleague.adobe.com/DootwtTj5kDIRHKhFPeY3Fnt3bWdVLsXc6J3UEc5LPI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 246
ht-degree: 100%

---

# Solução de problemas de implementações do Código H

Veja a seguir as etapas de solução de problemas específicas das implementações do Código H.

## Inserção do código do Analytics na marca do cabeçalho

>[!NOTE]
>
>Embora as implementações do Código H exijam a referência ao código na tag `<body>`, outras implementações (como o uso da Adobe Experience Platform ) exigem a referência do código na tag `<head>`.

O código do Analytics cria uma imagem invisível de 1x1 pixels. Anteriormente, uma prática comum de implementação era colocar a referência `s_code.js` na `<head>` tag. Colocar o código aqui impedia que a imagem afetasse o layout da página de qualquer forma. Além disso, ele é executado antes, permitindo a contagem de exibições de página para carregamentos parciais de página com mais eficiência.

No entanto, determinados elementos do código exigem a existência do objeto `<body>`. Se o código JavaScript do Analytics estiver na tag `<head>`, ele será executado antes que o objeto `<body>` exista. Como resultado, sua implementação não coletará os dados do [!UICONTROL ClickMap], o rastreamento automático dos downloads de arquivo ou links de saída ou dados de tipo de conexão. Inserir a referência de script `s_code.js` na tag `<head>` funciona, mas o resultado é uma versão muito limitada do Analytics.

O código do Analytics pode ser inserido em qualquer lugar dentro da tag `<body>` de uma página HTML bem formada. A Adobe recomenda colocar o código do Analytics o mais próximo possível da parte superior da tag `<body>`. Verifique se todas as variáveis de página estão definidas após o carregamento do arquivo `s_code.js`.

>[!TIP]
>
>Se quiser integrar o Adobe Analytics ao Adobe Target, o arquivo de inclusão do JavaScript deverá ser colocado na parte inferior da página.
