---
title: Fidelidade do cliente
description: Categorias com base no número de compras anteriores feitas por um visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 0%

---


# Fidelidade do cliente

A dimensão &quot;Fidelidade do cliente&quot; relata o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou 3+ compras anteriores. Essa dimensão é importante para entender como seu site afeta o comportamento de compra. Você também pode usar essa dimensão em um segmento para focar em visitantes que retornam para fazer uma compra, de modo que você possa incentivar comportamentos semelhantes para novos visitantes.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) evento em sua implementação. Se você implementar o `purchase` evento em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem o seguinte:

* **Não é um cliente**: No momento da ocorrência, o visitante nunca fez uma compra antes.
* **Novos clientes**: No momento da ocorrência, o visitante fez uma única compra antes.
* **Clientes** recorrentes: No momento da ocorrência, o visitante fez duas compras antes.
* **Clientes** fidelizados: No momento da ocorrência, o visitante fez três ou mais compras antes.

Quando um visitante efetua uma compra (aciona o `purchase` evento), essa ocorrência e todas as ocorrências subsequentes são movidas para o próximo &quot;bucket&quot;. Por exemplo, se um visitante comprar um produto de seu site pela primeira vez, ele mudará de &quot;Não é um cliente&quot; para &quot;Novos clientes&quot;, com o pedido atribuído a &quot;Novos clientes&quot;. O item de dimensão &quot;Não é um cliente&quot; não pode ter ordens atribuídas a ele.
