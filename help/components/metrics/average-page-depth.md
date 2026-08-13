---
title: Profundidade média da página
description: Em quantas páginas a dimensão existe em média.
feature: Metrics
exl-id: 6625405a-bda5-4723-8d22-4bc5b7e44d4e
TQID: https://experienceleague.adobe.com/Pm2WxRPqn9M-7IdrFQ2Tkj9t-L8ug3nZGr6ncpZg7lg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 365
ht-degree: 55%

---

# Profundidade média da página

A [métrica](overview.md) da &quot;Profundidade média da página&quot; mostra a que distância, em média, um item de dimensão se estende em uma determinada visita. Por exemplo, a página inicial (que é um item de dimensão para a dimensão Página ) normalmente mostra uma profundidade média de página menor do que a página Confirmação de compra, que provavelmente se estende ainda mais para uma visita. Você pode usar essas informações para otimizar determinadas páginas para visitantes novos se a página tiver uma profundidade baixa, em média.

>[!TIP]
>
>Use esta métrica junto com outra métrica, como [Visitas](visits.md), para obter melhores insights. Se essa métrica for utilizada sozinha, é possível obter itens de dimensão que contêm profundidades de página anômalas, o que geralmente não é uma insight valiosa.

## Como essa métrica é calculada

A primeira página de uma visita tem uma profundidade de página de `0`. A próxima página tem uma profundidade de página de 1 e ela aumenta a cada visualização de página até o final da visita. Essa métrica aumenta somente com chamadas de exibição de página ([`t()`](/help/implement/vars/functions/t-method.md)), e não com chamadas de rastreamento de link ([`tl()`](/help/implement/vars/functions/tl-method.md)).

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
