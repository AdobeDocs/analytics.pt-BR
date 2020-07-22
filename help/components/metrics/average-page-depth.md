---
title: Profundidade média da página
description: Quantas páginas em média a dimensão existe em.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---


# Profundidade média da página

A métrica &quot;Profundidade média de página&quot; mostra o quão distante em uma determinada visita o item de dimensão está. Por exemplo, seu home page normalmente mostraria uma profundidade média de página menor do que sua página de confirmação de compra, que normalmente seria mais detalhada em uma visita. Essa métrica é útil quando você deseja entender quantas páginas em um determinado item de dimensão se situam em média. Você pode usar essas informações para otimizar determinadas páginas em direção a visitantes novos se a página tiver uma profundidade baixa em média.

>[DICA] Use essa métrica junto com outra métrica (como [Visitas](visits.md)) para obter melhores insights. Se você usar essa métrica sozinho, você obterá itens de dimensão que contêm profundidades de página de anomalias, o que normalmente não é valioso.

## Como essa métrica é calculada

A primeira página de uma visita tem uma profundidade de página de `0`. A próxima página tem uma profundidade de página de 1 e aumenta cada visualização de página até o final da visita. Essa métrica só aumenta com chamadas de visualização de página ([`t()`](/help/implement/vars/functions/t-method.md)) e não com chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

Para um determinado item de dimensão, adicione todas as profundidades de página para esse item de dimensão e divida-o por visitas. O número resultante é a profundidade média da página, arredondada para o número inteiro mais próximo. Itens de dimensão com uma profundidade média de página `0` significa que eles estavam frequentemente na primeira página da visita.

Por exemplo, considere o seguinte exemplo de visita:

```text
Page1 > Page2 > Page2 > Page3 > Page4 > Page2
```

Se desejarmos a profundidade média da página para o item de dimensão `Page2`, ela será calculada da seguinte forma:

```text
If 'Count repeat instances' is enabled:
(1 + 2 + 5) / 3 = 2.67, rounded up to 3

If 'Count repeat instances' is disabled:
(1 + 4) / 2 = 2.5, rounded up to 3
```

>[!TIP]
>
>Se quiser ver a profundidade média da página com uma casa decimal, crie uma métrica calculada usando essa métrica como o único elemento dentro da fórmula. Aumente as casas decimais na métrica calculada para a casa decimal desejada.

## Porcentagens acima de 100%

Essa métrica frequentemente contém porcentagens acima de 100%. O denominador é a profundidade média de página de toda a dimensão, e o numerador é a profundidade média de página do item de dimensão. Se a profundidade média de página de toda a dimensão for inferior à profundidade média de página de um determinado item de dimensão, você verá percentuais acima de 100%. A classificação de relatórios classificados por essa métrica mostra os valores de profundidade média da página da anomalia, que normalmente não é valiosa. A Adobe recomenda classificar por outra métrica, como [Visitas](visits.md), em relatórios classificados.