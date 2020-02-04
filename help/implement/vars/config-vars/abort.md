---
title: aborto
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# aborto

A `abort` variável é um booleano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe.

## Usar a variável abortar no Adobe Experience Platform Launch

Não há um campo dedicado no Launch para usar essa variável. Use o editor de código personalizado, após a sintaxe do AppMeasurement.

## Sintaxe do AppMeasurement e editor de código personalizado no Launch

A `abort` variável é booleana. Its default value is `false`.

* Se definida como `true`, a próxima chamada de rastreamento (`t()` ou `tl()`) não enviará dados para a Adobe.
* Se definida como `false` ou não definida, essa variável não fará nada.

```js
s.abort = true;
```

> [!NOTE] A `abort` variável é redefinida para `false` depois de cada chamada de rastreamento. Se precisar abortar chamadas de rastreamento subsequentes na mesma página, defina `abort` para `true` novamente.

## Exemplo

A `abort` variável pode ser definida na `doPlugins()` função, que é a última função a ser executada antes que uma solicitação de imagem seja enviada para a Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Você pode centralizar a lógica usada para identificar atividades que não deseja rastrear, como links personalizados ou links externos em anúncios de exibição.
