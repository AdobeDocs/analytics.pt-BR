---
title: Altura do navegador - segmentado
description: A altura da janela do navegador em pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 0%

---


# Altura do navegador

A dimensão &#39;Altura do navegador - segmentado&#39; mostra a altura da janela do navegador, classificada em grupos de 100 pixels. Essa dimensão é útil quando você deseja entender onde a &quot;dobra&quot; está no site para os visitantes. Entender onde sua dobra está pode permitir otimizar o conteúdo para exibição.

Essa dimensão é diferente da altura da tela. Altura do navegador é o número de pixels dentro do espaço visualizável do navegador, enquanto a altura da tela é a altura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie + cole o seguinte código no console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

A altura do navegador é sempre menor ou igual à altura da tela, já que a altura do navegador não inclui a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da string [`bh` do](/help/implement/validate/query-parameters.md) query em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerHeight` no navegador. Se você usar uma biblioteca do AppMeasurement (por exemplo, por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você usar um método de coleta de dados fora do AppMeasurement (por exemplo, por meio da API), certifique-se de incluir o parâmetro da string de `bh` query na primeira ocorrência de cada visita.

A Adobe persiste na altura do navegador para uma visita. Se a altura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## Itens de dimensão

Os itens de dimensão incluem todas as alturas coletadas do navegador, classificadas em grupos de 100 pixels. Por exemplo, se a altura do navegador de uma ocorrência for `720`, então ela será agrupada no item de dimensão `700 to 799`.
