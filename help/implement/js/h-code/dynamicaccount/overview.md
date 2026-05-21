---
title: Visão geral das contas dinâmicas
description: Saiba mais sobre como selecionar dinamicamente um conjunto de relatórios usando o Código H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 100%

---

# Visão geral das contas dinâmicas

>[!IMPORTANT]
>
>As contas dinâmicas são compatíveis apenas com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem com as tags na Adobe Experience Platform.

As contas dinâmicas são um recurso de implementação que permite determinar qual conjunto de relatórios usar com base nos critérios definidos. Se sua organização exigir mais de um conjunto de relatórios, mas desejar usar a mesma implementação entre os sites, as contas dinâmicas são uma boa solução.

>[!TIP]
>
>A Adobe recomenda enviar dados para um único conjunto de relatórios, em seguida, usar conjuntos de relatórios virtuais para separar dados, se necessário. Consulte [Considerações do conjunto de relatórios global](../../../prepare/global-rs.md) para obter mais informações.

3 variáveis são usadas para selecionar dinamicamente um conjunto de relatórios.

* [`dynamicAccountSelection`](dynamicaccountselection.md): habilitar ou desabilitar a seleção de conta dinâmica.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): determina qual valor deve ser observado. Por exemplo, o URL ou uma cadeia de caracteres de consulta.
* [`dynamicAccountList`](dynamicaccountlist.md): compara os valores com `dynamicAccountMatch` e, se uma correspondência for encontrada, preenche a variável `account`.

Se `dynamicAccountSelection = true`, o valor em `dynamicAccountMatch` é comparado a `dynamicAccountList`. Se os valores em `dynamicAccountList` forem correspondentes, a ID do conjunto de relatórios será incluída na variável `account`.

## Conjunto de relatórios padrão

A variável `account` pode ser definida primeiro e atua como valor padrão, caso não seja possível encontrar uma das strings especificadas. Por exemplo:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Se `location.hostname` não fosse `dev.example.com` nem `example.com`, a ocorrência seria enviada para `examplersiddefault`.

## Marcação de vários relatórios

A marcação de vários relatórios pode ser usada com a seleção de conta dinâmica. Por exemplo:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Se `location.hostname` contém `example.com`, a ocorrência é enviada para `examplersid1` e `examplersid2`.
