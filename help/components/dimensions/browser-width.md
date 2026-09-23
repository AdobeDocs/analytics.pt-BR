---
title: Largura do navegador - Classificada
description: A largura da janela do navegador em pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
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
source-wordcount: '318'
ht-degree: 45%
---
# Largura da janela do navegador

A [dimensão](overview.md) de &#39;Largura do navegador - Classificada&#39; mostra a largura da janela do navegador classificada em grupos predefinidos. Essa dimensão é útil quando você quer entender como os visitantes veem seu conteúdo. Entender a largura em que seu conteúdo é normalmente exibido no pode permitir que você otimize esse conteúdo.

Essa dimensão é diferente da largura da tela. A largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a largura da tela é a largura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

A largura do navegador é sempre menor ou igual à largura da tela, já que a largura do navegador não inclui barras de rolagem ou bordas.

>[!NOTE]
>
>O Data Warehouse também fornece uma dimensão &#39;[!UICONTROL Largura do navegador - granular]&#39;, que relata a largura exata do pixel em vez de agrupar valores em compartimentos predefinidos.

## Preencher esta dimensão com dados

A largura do navegador é coletada automaticamente, no lado do cliente, da propriedade `window.innerWidth` do navegador. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie o valor na primeira ocorrência de cada visita. Se a largura do navegador for ajustada no meio da visita, o ajuste não será registrado.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`bw`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<browserWidth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Intervalo de valores** | 0-65.535 |
| **Persistência** | Visita |

## Itens de dimensão

Os itens do Dimension incluem todas as larguras do navegador coletadas, classificadas em grupos predefinidos. Por exemplo, se a largura do navegador de um hit for `1280`, então ela será agrupada no item de dimensão `1200 to 1299`.
