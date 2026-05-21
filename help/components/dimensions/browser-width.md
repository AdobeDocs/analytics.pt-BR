---
title: Largura do navegador - Classificada
description: A largura da janela do navegador em pixels.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 81%

---

# Largura da janela do navegador

A [dimensão](overview.md) de &#39;Largura do navegador - Classificada&#39; mostra a largura da janela do navegador classificada em grupos predefinidos. Essa dimensão é útil quando você quer entender como os visitantes veem seu conteúdo. Entender a largura em que seu conteúdo é normalmente exibido no pode permitir que você otimize esse conteúdo.

Essa dimensão é diferente da largura da tela. A largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a largura da tela é a largura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

A largura do navegador é sempre menor ou igual à largura da tela, já que a largura do navegador não inclui barras de rolagem ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`bw` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerWidth` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados diferente do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `bw` na primeira ocorrência de cada visita.

A Adobe mantém a largura do navegador para uma visita. Se a largura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## Itens de dimensão

Os itens do Dimension incluem todas as larguras do navegador coletadas, classificadas em grupos predefinidos. Por exemplo, se a largura do navegador de uma ocorrência for `1280`, então ela será agrupada no item de dimensão `1200 to 1299`.
