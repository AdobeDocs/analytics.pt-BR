---
title: Altura do navegador - Classificada
description: A altura da janela do navegador em pixels.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 273
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

Os itens do Dimension incluem todas as alturas do navegador coletadas, classificadas em grupos predefinidos. Por exemplo, se a altura do navegador de uma ocorrência for `720`, então ela será agrupada no item de dimensão `700 to 799`.
