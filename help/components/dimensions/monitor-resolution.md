---
title: Resolução do monitor
description: A resolução do monitor do visitante em pixels.
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
source-git-commit: e6f3beadfba340cea07f5fd2694105ad31de9751
workflow-type: tm+mt
source-wordcount: '240'
ht-degree: 91%

---

# Resolução do monitor

A dimensão “Resolução do monitor” mostra a altura e a largura da exibição ativa em pixels. Essa dimensão é útil quando você deseja entender onde está a “dobra” em seu site para os visitantes ou a largura máxima da janela do navegador dos visitantes. Entender onde a dobra está pode permitir a otimização do conteúdo para exibição.

Essa dimensão é diferente da altura e da largura do navegador. Altura/largura do navegador é o número de pixels dentro do espaço visível do navegador, enquanto a resolução do monitor é o número de pixels de todo o monitor. Se você quiser ver a diferença entre essas duas variáveis em seu próprio computador, abra o console do navegador (F12 na maioria dos navegadores) e copie e cole o seguinte código no console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "\nBrowser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

As dimensões do navegador são sempre menores que a resolução do monitor, já que as dimensões do navegador não incluem a navegação do navegador ou bordas.

## Preencher esta dimensão com dados

Essa dimensão recupera dados da [`s` sequência de consulta](/help/implement/validate/query-parameters.md) em solicitações de imagem. O AppMeasurement coleta esses dados usando a variável JavaScript `screen.width` e `screen.height` no navegador. Se você usar uma biblioteca do AppMeasurement (por meio de tags no Adobe Experience Platform), essa dimensão funcionará imediatamente. Se um método de coleta de dados diferente do AppMeasurement for utilizado (por meio da API), inclua o parâmetro da sequência de consulta `s` em solicitações de imagem.

## Itens de dimensão

Os itens de dimensão incluem todas as resoluções de monitor coletadas. Os valores de exemplo incluem `1920 x 1080`, `1366 x 768` e `1280 x 720`.
