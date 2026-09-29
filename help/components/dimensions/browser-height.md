---
title: Altura do navegador - Classificada
description: A altura da janela do navegador em pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: 'https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
source-wordcount: '318'
ht-degree: 40%
---
# Altura da janela do navegador

A [dimensão](overview.md) de &#39;Altura do navegador - classificada&#39; mostra a altura da janela do navegador, classificada em grupos predefinidos. Essa dimensão é útil para entender onde está a &quot;dobra&quot; no site para os visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Essa dimensão é diferente da altura da tela. Altura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a altura da tela é a altura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

A altura do navegador normalmente é menor ou igual à altura da tela, já que a altura do navegador não inclui a navegação do navegador ou bordas.

>[!NOTE]
>
>O Data Warehouse também fornece uma dimensão &#39;[!UICONTROL Altura do navegador - granular]&#39;, que relata a altura exata do pixel em vez de agrupar valores em compartimentos predefinidos.

## Preencher esta dimensão com dados

A altura do navegador é coletada automaticamente, no lado do cliente, da propriedade `window.innerHeight` do navegador. Funciona imediatamente em qualquer implementação do AppMeasurement ou da Web SDK (tags) — não há variável para definir. Se você coletar dados fora do AppMeasurement ou da Web SDK (por exemplo, por meio da API), envie o valor na primeira ocorrência de cada visita. Se a altura do navegador for ajustada no meio da visita, o ajuste não será registrado.

| Propriedade | Valor |
| --- | --- |
| **Variável do AppMeasurement** | Nenhum (coletado automaticamente) |
| **Web SDK / campo XDM** | Nenhum (coletado automaticamente) |
| **Parâmetro de consulta** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Marca XML** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Intervalo de valores** | 0-65.535 |
| **Persistência** | Visita |

## Itens de dimensão

Os itens do Dimension incluem todas as alturas do navegador coletadas, classificadas em grupos predefinidos. Por exemplo, se a altura do navegador de um hit for `720`, será agrupado no item de dimensão `700 to 799`.
