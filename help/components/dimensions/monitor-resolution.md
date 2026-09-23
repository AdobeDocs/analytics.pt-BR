---
title: Resolução do monitor
description: A resolução do monitor do visitante em pixels.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 51%
---
# Resolução do monitor

A [dimensão](overview.md) da &#39;Resolução do monitor&#39; mostra a altura e a largura da exibição ativa em pixels. Essa dimensão é útil quando você deseja entender onde está a “dobra” em seu site para os visitantes ou a largura máxima da janela do navegador dos visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Esta dimensão é diferente da [altura](browser-height.md) e da [largura](browser-width.md) do navegador. Altura/largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a resolução do monitor é o número de pixels de todo o monitor. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

As dimensões do navegador são sempre menores que a resolução do monitor, já que as dimensões do navegador não incluem a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

A resolução do monitor é coletada automaticamente, no lado do cliente, das propriedades `screen.width` e `screen.height` do navegador. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie o valor em solicitações de imagem. Se estiver ausente ou se uma biblioteca de coleta de dados não puder coletar a resolução do monitor, esses dados serão listados em [!UICONTROL `Not Specified`].

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite de bytes** | 20 bytes |
| **Persistência** | N/D |

## Itens de dimensão

Os itens de dimensão incluem todas as resoluções de monitor coletadas. Os valores de exemplo incluem `1920 x 1080`, `1366 x 768` e `1280 x 720`.
