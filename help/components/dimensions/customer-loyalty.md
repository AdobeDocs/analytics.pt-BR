---
title: Fidelização do cliente
description: Categorias com base no número de compras anteriores feitas por um visitante
exl-id: 48ac1fdf-9a32-4bcc-8b23-bf58358a3470
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '242'
ht-degree: 100%

---

# Fidelização do cliente

A dimensão “Fidelidade do cliente” informa o número de visitantes do site que fizeram 0 compras anteriores, 1 compra anterior, 2 compras anteriores ou mais de 3 compras anteriores. Essa dimensão é importante para entender como seu site afeta o comportamento de compra. Você também pode usar essa dimensão em um segmento para se concentrar em visitantes que retornam para fazer uma compra, de modo que você possa incentivar comportamentos semelhantes para novos visitantes.

## Preencher esta dimensão com dados

A Adobe preenche automaticamente essa dimensão com base no evento [`purchase`](/help/implement/vars/page-vars/events/event-purchase.md) em sua implementação. Se você implementar o evento `purchase` em seu site, essa dimensão sempre funcionará.

## Itens de dimensão

Os itens de dimensão incluem:

* **Não é um cliente**: no momento da ocorrência, o visitante nunca tinha feito uma compra antes.
* **Novos clientes**: no momento da ocorrência, o visitante tinha feito uma única compra antes.
* **Clientes recorrentes**: no momento da ocorrência, o visitante tinha feito duas compras antes.
* **Clientes fiéis**: no momento da ocorrência, o visitante tinha feito três ou mais compras antes.

Quando um visitante faz uma compra (aciona o `purchase` evento), essa ocorrência e todas as ocorrências subsequentes são movidas para a próxima “classificação”. Por exemplo, se um visitante comprar um produto do seu site pela primeira vez, ele mudará de “Não é um cliente” para “Novos clientes”, com o pedido atribuído a “Novos clientes”. O item de dimensão “Não é um cliente” não pode ter ordens atribuídas a ele.
