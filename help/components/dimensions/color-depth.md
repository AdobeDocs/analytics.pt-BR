---
title: Intensidade de cor
description: A intensidade de cor do dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: null
workflow-type: tm+mt
source-wordcount: 228
ht-degree: 94%

---

# Intensidade de cor

A [dimensão](overview.md) de &#39;Intensidade de cor&#39; relata quantas cores o dispositivo aceita. Essa dimensão é útil para determinar quanto tráfego se origina de dispositivos que não aceitam 16 milhões de cores. Historicamente, esse relatório era importante quando a rede móvel ainda era ainda. No entanto, a maioria dos dispositivos atuais aceita 16 milhões de cores (0 a 255 para vermelho, verde e azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Preencher esta dimensão com dados

Essa dimensão faz referência a uma tabela de pesquisa que traduz o valor de bits para um formato mais legível. Ele coleta dados da [`c` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement usa a variável `screen.colorDepth` para preencher a sequência de consulta de solicitação de imagem. Se você utilizar o AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará automaticamente. Se você utilizar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `c` em cada ocorrência com um valor de bits válido.

## Itens de dimensão

Os itens de dimensão incluem o número de cores aceito pelo dispositivo. Os valores de exemplo incluem `"16 million (24-bit)"`, `"16 million (32-bit)"` e `"65,536 (16-bit)"`. Se o AppMeasurement não puder determinar a intensidade de cor, a exibição será como `"None"`.

>[!TIP]
>
>A diferença entre a compatibilidade com 24 e 32 bits é que 32 bits é compatível com um canal alpha (RGBA), enquanto o de 24 bits não (RGB). Consulte [Intensidade de cor](https://pt.wikipedia.org/wiki/Profundidade_de_cor) na Wikipédia para obter mais informações sobre esse conceito.
