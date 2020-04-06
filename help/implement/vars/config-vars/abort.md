---
title: abort
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# abort

A variável `abort` é um booleano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe.

## Usar a variável abort no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## Sintaxe do AppMeasurement e editor de código personalizado no Launch

A variável `abort` é booleana. O valor padrão é `false`.

* Se definida como `true`, a próxima chamada de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) não enviará dados para a Adobe.
* Se definida como `false` ou não definida, essa variável não fará nada.

```js
s.abort = true;
```

>[!NOTE] A `abort` variável é redefinida para `false` depois de cada chamada de rastreamento. Se precisar abortar chamadas de rastreamento subsequentes na mesma página, defina `abort` como `true` novamente.

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
