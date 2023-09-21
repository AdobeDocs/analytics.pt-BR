---
title: Profundidade média da página
description: Em quantas páginas a dimensão existe em média.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 60%

---

# Profundidade média da página

A &quot;Profundidade média da página&quot; [métrica](overview.md) mostra até que ponto um item de dimensão se estende em uma determinada visita, em média. Por exemplo, a página inicial (que é um item de dimensão para a dimensão Página ) normalmente mostra uma profundidade média de página menor do que a página Confirmação de compra, que provavelmente se estende ainda mais para uma visita. Você pode usar essas informações para otimizar determinadas páginas para visitantes novos se a página tiver uma profundidade baixa, em média.

>[!TIP]
>
>Use essa métrica junto com outra métrica, como [Visitas](visits.md), para obter melhores insights. Se essa métrica for utilizada sozinha, é possível obter itens de dimensão que contêm profundidades de página anômalas, o que geralmente não é um insight valioso.

## Como essa métrica é calculada

A primeira página de uma visita tem uma profundidade de página de `0`. A próxima página tem uma profundidade de página de 1 e ela aumenta a cada visualização de página até o final da visita. Essa métrica aumenta somente com a exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)), e não com o rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)) chamadas.

Para um determinado item de dimensão, adicione todas as profundidades de página para esse item de dimensão e divida-o por visitas. O número resultante é a profundidade média da página, arredondada para o número inteiro mais próximo. Itens de dimensão com uma profundidade média de página `0` significa que eram frequentes na primeira página da visita.

Por exemplo, considere o seguinte exemplo de visita:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se quisermos determinar a profundidade média da página para o item da dimensão `Page2`, ela será calculada da seguinte forma:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Se quiser saber a profundidade média da página com uma casa decimal, crie uma métrica calculada utilizando essa métrica como o único elemento dentro da fórmula. Aumente as casas decimais na métrica calculada para o decimal desejado.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a profundidade média da página da dimensão inteira, e o numerador é a profundidade média da página no item de dimensão.

Se a profundidade média da página de toda a dimensão for menor que a profundidade média da página de um determinado item de dimensão, você verá porcentagens acima de 100%. A classificação de relatórios classificados por essa métrica mostra valores de profundidade média da página com anomalias, o que geralmente não é útil. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.
