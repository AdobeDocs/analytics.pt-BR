---
description: Lista de eventos predefinidos.
keywords: Analytics Implementation;event
solution: Analytics
title: O que é um evento predefinido?
topic: Developer and implementation
uuid: 4d0799ba-0f97-42c3-a620-36c03f9995da
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# O que é um evento predefinido?

Lista de eventos predefinidos.

| prodView | O evento bem-sucedido ocorre quando um visitante exibe um produto. |
|---|---|
| scView | O evento bem-sucedido ocorre quando um carrinho de compras é visualizado. |
| scOpen | O evento bem-sucedido ocorre sempre que um visitante abre um carrinho de compra pela primeira vez. |
| scAdd | O evento bem-sucedido ocorre quando um produto é adicionado a um carrinho de compras. |
| scRemove | O evento bem-sucedido ocorre sempre que um item é retirado de um carrinho de compras. |
| scCheckout | O evento bem-sucedido ocorre na primeira página de um check-out. |
| purchase | O evento bem-sucedido ocorre na página final do check-out (inclui Receita, Pedidos e Unidades). |

Quando um dos eventos predefinidos ocorrer, uma instância do evento será aumentada. É possível exibir as métricas de conversão relacionadas ao evento em vários relatórios diferentes. Consulte abaixo um exemplo do código usado para configurar eventos predefinidos.

```js
s.events="scAdd"
```

```js
s.events="scOpen,scAdd"
```

* No primeiro exemplo acima, *`scAdd`*&#x200B;é o valor do evento. Sempre que um item é adicionado ao carrinho, o evento é incrementado.
* No segundo exemplo, são capturados dois valores simultaneamente. Quando vários eventos de sucesso ocorrem na mesma página, cada evento é aumentado.

