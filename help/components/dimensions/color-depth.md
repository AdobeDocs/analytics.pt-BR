---
title: Intensidade de cor
description: A intensidade de cor do dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: 'https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 52%
---
# Intensidade de cor

A [dimensão](overview.md) de &#39;Intensidade de cor&#39; relata quantas cores o dispositivo aceita. Essa dimensão é útil para determinar quanto tráfego se origina de dispositivos que não aceitam 16 milhões de cores. Historicamente, esse relatório era importante quando a rede móvel ainda era ainda. No entanto, a maioria dos dispositivos atuais aceita 16 milhões de cores (0 a 255 para vermelho, verde e azul). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Preencher esta dimensão com dados

A intensidade de cor é coletada automaticamente, no lado do cliente, da propriedade `screen.colorDepth` do navegador, que o Adobe traduz por meio de uma tabela de pesquisa em um formato legível. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie um valor de bit válido em cada ocorrência.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`c`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<colorDepth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 20 bytes |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem o número de cores aceito pelo dispositivo. Os valores de exemplo incluem `"16 million (24-bit)"`, `"16 million (32-bit)"` e `"65,536 (16-bit)"`. Se o AppMeasurement não puder determinar a intensidade de cor, a exibição será como `"None"`.

>[!TIP]
>
>A diferença entre a compatibilidade com 24 e 32 bits é que 32 bits é compatível com um canal alpha (RGBA), enquanto o de 24 bits não (RGB). Consulte [Intensidade de cor](https://pt.wikipedia.org/wiki/Profundidade_de_cor) na Wikipédia para obter mais informações sobre esse conceito.
