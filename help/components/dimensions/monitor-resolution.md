---
title: Resolução do monitor
description: A resolução do monitor do visitante em pixels.
translation-type: ht
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: ht
source-wordcount: '239'
ht-degree: 100%

---


# Resolução do monitor

A dimensão “Resolução do monitor” mostra a altura e a largura da exibição ativa em pixels. Essa dimensão é útil quando você deseja entender onde está a “dobra” em seu site para os visitantes ou a largura máxima da janela do navegador dos visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Essa dimensão é diferente da altura e da largura do navegador. Altura/largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a resolução do monitor é o número de pixels de todo o monitor. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

As dimensões do navegador são sempre menores que a resolução do monitor, já que as dimensões do navegador não incluem a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`s` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `screen.width` e `screen.height` no navegador. Se você utilizar uma biblioteca do AppMeasurement (por meio do Adobe Experience Platform Launch), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `s` em solicitações de imagem.

## Itens de dimensão

Os itens de dimensão incluem todas as resoluções de monitor coletadas. Os valores de exemplo incluem `1920 x 1080`, `1366 x 768` e `1280 x 720`.
