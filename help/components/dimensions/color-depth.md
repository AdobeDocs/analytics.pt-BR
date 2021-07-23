---
title: Intensidade de cor
description: A intensidade de cor do dispositivo.
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 91%

---

# Intensidade de cor

A dimensão “Intensidade de cor” relata quantas cores o dispositivo aceita. Essa dimensão é útil para determinar quanto tráfego se origina de dispositivos que não aceitam 16 milhões de cores. Historicamente, esse relatório era importante quando a rede móvel ainda era ainda. No entanto, a maioria dos dispositivos atuais aceita 16 milhões de cores (0 a 255 para vermelho, verde e azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa que traduz o valor de bits para um formato mais legível. Ele coleta dados da [`c` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement usa a variável `screen.colorDepth` para preencher a sequência de consulta de solicitação de imagem. Se você usar o AppMeasurement (por exemplo, por meio de tags no Adobe Experience Platform), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `c` em cada ocorrência com um valor de bits válido.

## Itens de dimensão

Os itens de dimensão incluem o número de cores aceito pelo dispositivo. Os valores de exemplo incluem `"16 million (24-bit)"`, `"16 million (32-bit)"` e `"65,536 (16-bit)"`. Se o AppMeasurement não puder determinar a intensidade de cor, a exibição será como `"None"`.

>[!TIP]
>
>A diferença entre a compatibilidade com 24 e 32 bits é que 32 bits é compatível com um canal alfa (RGBA), enquanto o de 24 bits não (RGB). Consulte [Intensidade de cor](https://pt.wikipedia.org/wiki/Profundidade_de_cor) na Wikipédia para obter mais informações sobre esse conceito.
