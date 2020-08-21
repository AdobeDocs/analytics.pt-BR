---
title: Largura do navegador - Classificada
description: A largura da janela do navegador em pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 88%

---


# Largura do navegador

A dimensão “Largura do navegador - Classificada” mostra a largura da janela do navegador classificada em grupos de 100 pixels. Essa dimensão é útil quando você quer entender como os visitantes veem seu conteúdo. Compreender a largura em que seu conteúdo é tipicamente exibido pode permitir otimizar o conteúdo para exibição.

Essa dimensão é diferente da largura da tela. A largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a largura da tela é a largura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

A largura do navegador é sempre menor ou igual à largura da tela, já que a largura do navegador não inclui barras de rolagem ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`bw` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerWidth` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados diferente do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `bw` na primeira ocorrência de cada visita.

A Adobe mantém a largura do navegador para uma visita. Se a largura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## itens de Dimension

Os itens de Dimension incluem todas as larguras coletadas do navegador, classificadas em grupos de 100 pixels. For example, if the browser width of a hit is `1280`, then it is grouped in the dimension item `1200 to 1299`.
