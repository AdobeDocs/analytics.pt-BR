---
title: abort
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 79%

---

# abort

A variável `abort` é um booleano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe.

## Uso da variável abort na interface do usuário da coleta de dados no Adobe Experience Platform

Não há um campo dedicado na interface do usuário da coleta de dados para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## Sintaxe do AppMeasurement e editor de código personalizado na interface do usuário da coleta de dados

A variável `abort` é booleana. O valor padrão é `false`.

* Se definida como `true`, a próxima chamada de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) não enviará dados para a Adobe.
* Se definida como `false` ou não definida, essa variável não fará nada.

```js
s.abort = true;
```

>[!NOTE]
>
>A variável `abort` é redefinida para `false` depois de cada chamada de rastreamento. Se precisar abortar chamadas de rastreamento subsequentes na mesma página, defina `abort` como `true` novamente.

## Exemplo

A variável `abort` pode ser definida na função [`doPlugins()`](../functions/doplugins.md), que é a última a ser executada antes que uma solicitação de imagem seja enviada para a Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.
