---
title: Altura do navegador - Classificada
description: A altura da janela do navegador em pixels.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 88%

---


# Altura do navegador

A dimensão “Altura do navegador - classificada” exibe a altura da janela do navegador, classificada em grupos de 100 pixels. Essa dimensão é útil para entender onde está a &quot;dobra&quot; no site para os visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Essa dimensão é diferente da altura da tela. Altura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a altura da tela é a altura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

A altura do navegador é sempre menor ou igual à altura da tela, já que a altura do navegador não inclui a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`bh` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerHeight` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados diferente do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `bh` na primeira ocorrência de cada visita.

A Adobe mantém a altura do navegador por uma visita. Se a altura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## itens de Dimension

Os itens de Dimension incluem todas as alturas coletadas do navegador, classificadas em grupos de 100 pixels. For example, if the browser height of a hit is `720`, then it is grouped in the dimension item `700 to 799`.
