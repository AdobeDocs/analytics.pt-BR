---
title: Altura do navegador - Classificada
description: A altura da janela do navegador em pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
source-git-commit: 2601b0e5c3fa78237ce693801b8dd8c95b853b81
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 87%

---

# Altura da janela do navegador

A [dimensão](overview.md) de &#39;Altura do navegador - classificada&#39; mostra a altura da janela do navegador, classificada em grupos predefinidos. Essa dimensão é útil para entender onde está a &quot;dobra&quot; no site para os visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Essa dimensão é diferente da altura da tela. Altura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a altura da tela é a altura do monitor inteiro em pixels. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

A altura do navegador é sempre menor ou igual à altura da tela, já que a altura do navegador não inclui a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`bh` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `window.innerHeight` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio de tags na Adobe Experience Platform ), essa dimensão funcionará imediatamente. Se você utilizar um método de coleta de dados diferente do AppMeasurement (por exemplo, por meio da API), inclua o parâmetro da sequência de consulta `bh` na primeira ocorrência de cada visita.

A Adobe mantém a altura do navegador por uma visita. Se a altura do navegador for ajustada no meio da visita, o ajuste não será registrado.

## Itens de dimensão

Os itens de Dimension incluem todas as alturas do navegador coletadas, classificadas em grupos predefinidos. Por exemplo, se a altura do navegador de uma ocorrência for `720`, então ela será agrupada no item de dimensão `700 to 799`.
