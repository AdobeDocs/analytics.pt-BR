---
title: Visão geral das contas dinâmicas
description: Saiba mais sobre como selecionar dinamicamente um conjunto de relatórios usando o Código H.
translation-type: ht
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# Visão geral das contas dinâmicas

> [!IMPORTANT] As contas dinâmicas só compatíveis com implementações JavaScript herdadas (Código H). Essas variáveis não são compatíveis com as bibliotecas atuais do AppMeasurement nem no Adobe Experience Platform Launch.

As contas dinâmicas são um recurso de implementação que permite determinar qual conjunto de relatórios usar com base nos critérios definidos. Se sua organização exigir mais de um conjunto de relatórios, mas desejar usar a mesma implementação entre os sites, as contas dinâmicas são uma boa solução.

> [!TIP] A Adobe recomenda enviar dados para um único conjunto de relatórios, em seguida, usar conjuntos de relatórios virtuais para separar dados, se necessário. Consulte [Considerações do conjunto de relatórios global](../../../prepare/global-rs.md) para obter mais informações.

3 variáveis são usadas para selecionar dinamicamente um conjunto de relatórios.

* [`dynamicAccountSelection`](dynamicaccountselection.md): ativar ou desativar a seleção de conta dinâmica.
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
