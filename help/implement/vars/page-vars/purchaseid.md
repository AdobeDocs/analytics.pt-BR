---
title: purchaseID
description: Desduplicar ocorrências com base em um identificador de compra exclusivo.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '257'
ht-degree: 100%

---

# purchaseID

A variável `purchaseID` ajuda a impedir que ocorrências que contêm a mesma compra inflem os relatórios. Por exemplo, se um visitante acessa a página de confirmação de compra, são enviados dados sobre a receita gerada da transação para a Adobe. Se o usuário atualizar esta página várias vezes ou se marcar como favorito a página para visitá-la posteriormente, essas ocorrências podem aumentar os relatórios. A variável `purchaseID` remove a duplicação de métricas quando mais de uma ocorrência tem a mesma ID de compra.

Quando a Adobe reconhece uma ocorrência como uma compra duplicada, nenhum dado de conversão (como eVars e eventos) é exibido no relatório. Nos feeds de dados, a coluna `duplicate_purchase` é definida como `1`.

As IDs de compra se aplicam a todos os visitantes e não expiram. Se um visitante definir uma determinada ID de compra e um visitante diferente definir essa mesma ID de compra um ano depois, a segunda compra será desduplicada.

## ID de compra usando tags na Adobe Experience Platform

Não há um campo dedicado na interface da Coleção de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.purchaseID no AppMeasurement e no editor de código personalizado do 

A variável `s.purchaseID` é uma string que contém um identificador exclusivo para uma compra. Ela é definida na mesma ocorrência que um evento de compra. Use somente caracteres alfanuméricos para preencher essa variável.

Essa variável pode armazenar no máximo 20 bytes; valores maiores que 20 bytes são truncados. Se esse valor truncado corresponder aos valores truncados subsequentes, essas ocorrências subsequentes serão desduplicadas.

```js
s.purchaseID = "ABC123";
```

Se estiver usando a `digitalData` [camada de dados](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Não use uma função de geração de valores aleatórios para gerar uma ID de compra.
