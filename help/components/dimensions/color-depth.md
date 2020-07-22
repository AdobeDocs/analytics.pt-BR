---
title: Intensidade de cor
description: A intensidade de cor do dispositivo.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Intensidade de cor

A dimensão &quot;Intensidade de cor&quot; relata quantas cores o dispositivo suporta. Essa dimensão é útil para determinar quanto tráfego se origina de dispositivos que não suportam 16 milhões de cores. Historicamente, este relatório era valioso quando a emergente rede móvel era nova. no entanto, a maioria dos dispositivos na idade atual suporta 16 milhões de cores (0-255 para vermelho, verde e azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa, traduzindo o valor de bit em um formato mais legível. Ele coleta dados da string [`c` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement usa a `screen.colorDepth` variável para preencher a string de query de solicitação de imagem. Se você usar o AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `c` query em cada ocorrência com um valor de bit válido.

## Itens de dimensão

Os itens de dimensão incluem o número de cores suportadas pelo dispositivo. Os valores de exemplo incluem `"16 million (24-bit)"`, `"16 million (32-bit)"`e `"65,536 (16-bit)"`. Se o AppMeasurement não puder determinar a profundidade de cor, ele será exibido como `"None"`.

>[!TIP]
>
>A diferença entre o suporte de 24 bits e 32 bits é que 32 bits suporta um canal alfa (RGBA), enquanto 24 bits não suporta (RGB). Consulte Profundidade [](https://en.wikipedia.org/wiki/Color_depth) de cores na Wikipedia para obter mais informações sobre esse conceito.
