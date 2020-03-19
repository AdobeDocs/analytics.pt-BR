---
title: aborto
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# aborto

A `abort` variável é um booleano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe.

## Usar a variável abortar no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## Sintaxe do AppMeasurement e editor de código personalizado no Launch

A `abort` variável é booleana. Its default value is `false`.

* Se definida como `true`, a próxima chamada de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) não enviará dados para a Adobe.
* Se definida como `false` ou não definida, essa variável não fará nada.

```js
s.abort = true;
```

> [!NOTE] A `abort` variável é redefinida para `false` depois de cada chamada de rastreamento. Se precisar abortar as chamadas de rastreamento subsequentes na mesma página, defina `abort` para `true` novamente.

## Exemplo

A `abort` variável pode ser definida na [`doPlugins()`](../functions/doplugins.md) função, que é a última função a ser executada antes que uma solicitação de imagem seja enviada para a Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Você pode centralizar a lógica usada para identificar atividades que não deseja rastrear, como links personalizados ou links externos em anúncios de exibição.
