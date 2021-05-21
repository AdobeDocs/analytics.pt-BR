---
title: Largura do navegador - Classificada
description: A largura da janela do navegador em pixels.
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Largura da janela do navegador

A dimensão “Largura do navegador - Classificada” mostra a largura da janela do navegador classificada em grupos de 100 pixels. Essa dimensão é útil quando você quer entender como os visitantes veem seu conteúdo. Compreender a largura em que seu conteúdo é tipicamente exibido pode permitir otimizar o conteúdo para exibição.

Essa dimensão é diferente da largura da tela. A largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a largura da tela é a largura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
"Browser width: " + window.innerWidth + " pixels\nScreen width: " + screen.width + " pixels";
```

A largura do navegador é sempre menor ou igual à largura da tela, já que a largura do navegador não inclui barras de rolagem ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`bw` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerWidth` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados diferente do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `bw` na primeira ocorrência de cada visita.

A Adobe mantém a largura do navegador para uma visita. Se a largura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## Itens de dimensão

Os itens de dimensão incluem todas as larguras do navegador coletadas, classificadas em grupos de 100 pixels. Por exemplo, se a largura do navegador de uma ocorrência for `1280`, então ela será agrupada no item de dimensão `1200 to 1299`.
