---
title: Largura do navegador - segmentado
description: A largura da janela do navegador em pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Largura do navegador

A dimensão &#39;Largura do navegador - segmentada&#39; mostra a largura da janela do navegador, classificada em grupos de 100 pixels. Essa dimensão é útil quando você deseja entender a amplitude dos visitantes que veem seu conteúdo. Compreender a largura em que seu conteúdo é tipicamente exibido pode permitir que você otimize o conteúdo para exibição.

Essa dimensão é diferente da largura da tela. A largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a largura da tela é a largura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie + cole o seguinte código no console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

A largura do navegador é sempre menor ou igual à largura da tela, já que a largura do navegador não inclui barras de rolagem ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`bw` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerWidth` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `bw` query na primeira ocorrência de cada visita.

A Adobe persiste na largura do navegador para uma visita. Se a largura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## Itens de dimensão

Os itens de dimensão incluem todas as larguras coletadas do navegador, classificadas em grupos de 100 pixels. Por exemplo, se a largura de um navegador de uma ocorrência for `1280`, ele será agrupado no item de dimensão `1200 to 1299`.
