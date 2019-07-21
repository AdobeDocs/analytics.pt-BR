---
description: Lista de eventos predefinidos.
keywords: Implementação do Analytics; evento
seo-description: Lista de eventos predefinidos.
seo-title: O que é um evento predefinido?
solution: Analytics
title: O que é um evento predefinido?
topic: Desenvolvedor e implementação
uuid: 4 d 0799 ba -0 f 97-42 c 3-a 620-36 c 03 f 9995 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

