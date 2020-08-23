---
title: Profundidade média da página
description: Em quantas páginas a dimensão existe em média.
translation-type: tm+mt
source-git-commit: 226bbce18750825d459056ac2a87549614eb3c2c
workflow-type: tm+mt
source-wordcount: '369'
ht-degree: 55%

---


# Profundidade média da página

A métrica &quot;Profundidade média de página&quot; mostra o quão distante em uma determinada visita o item de dimensão está. Por exemplo, geralmente, a página inicial mostraria uma profundidade média de página menor do que a página de confirmação de compra, que normalmente seria mais distante em uma visita. Essa métrica é útil quando você deseja entender quantas páginas em um determinado item de dimensão se situam em média. É possível utilizar essas informações para otimizar determinadas páginas para visitantes novos se a página tiver em média uma baixa profundidade.

>[!TIP]
>
>Use this metric alongside another metric (such as [Visits](visits.md)) to obtain better insights. Se você usar essa métrica sozinho, você obterá itens de dimensão que contêm profundidades de página de anomalias, o que normalmente não é valioso.

## Como essa métrica é calculada

A primeira página de uma visita tem uma profundidade de página de `0`. A próxima página tem uma profundidade de página de 1 e ela aumenta a cada visualização de página até o final da visita. Essa métrica só aumenta com chamadas de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)), e não com chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Para um determinado item de dimensão, adicione todas as profundidades de página para esse item de dimensão e divida-o por visitas. O número resultante é a profundidade média da página, arredondada para o número inteiro mais próximo. Dimension items with an average page depth of `0` means it was frequently on the first page of the visit.

Por exemplo, considere o seguinte exemplo de visita:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

If we wanted average page depth for the dimension item `Page2`, it would be calculated as follows:

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

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a profundidade média de página de toda a dimensão, e o numerador é a profundidade média de página do item de dimensão. Se a profundidade média de página de toda a dimensão for inferior à profundidade média de página de um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra valores de profundidade média da página com anomalias, o que geralmente não é útil. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.