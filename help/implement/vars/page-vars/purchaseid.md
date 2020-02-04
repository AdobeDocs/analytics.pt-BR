---
title: purchaseID
description: Desduplicar ocorrências com base em um identificador de compra exclusivo.
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# purchaseID

A `purchaseID` variável ajuda a impedir que ocorrências que contêm a mesma compra aumentem os relatórios. Por exemplo, se um visitante acessar a página de confirmação de compra, você normalmente envia dados sobre a receita gerada da transação para a Adobe. Se o usuário atualizar esta página várias vezes ou marcar a página para visitá-la posteriormente, essas ocorrências podem aumentar os relatórios. A `purchaseID` variável remove a duplicação de métricas quando mais de uma ocorrência tem a mesma ID de compra.

Quando a Adobe reconhece uma ocorrência como uma compra duplicada, todos os dados de conversão (como eVars e eventos) não são exibidos no relatório. Nos feeds de dados, a `duplicate_purchase` coluna é definida como `1`.

As IDs de compra se aplicam a todos os visitantes e não expiram. Se um visitante definir uma determinada ID de compra, um visitante diferente definirá essa mesma ID de compra um ano depois, a segunda compra será deduplicada.

## ID de compra no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## s.purchaseID no AppMeasurement e no editor de código personalizado Iniciar

A `s.purchaseID` variável é uma string que contém um identificador exclusivo para uma compra. Ele é definido na mesma ocorrência que um evento de compra. Use somente caracteres alfanuméricos para preencher essa variável.

Essa variável pode armazenar no máximo 20 bytes; valores maiores que 20 bytes são truncados. Se esse valor truncado corresponder aos valores truncados subsequentes, essas ocorrências subsequentes serão deduplicadas.

```js
s.purchaseID = "ABC123";
```

> [!NOTE] Não use uma função de aleatoriedade para gerar uma ID de compra. Adobe recommends using a [data layer](../../prepare/data-layer.md) to store a given purchase ID.
