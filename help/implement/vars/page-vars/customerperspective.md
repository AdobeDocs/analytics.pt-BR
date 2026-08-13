---
title: customerPerspective
description: Especifica se uma ocorrência do aplicativo móvel ocorreu enquanto o aplicativo estava em primeiro ou segundo plano.
feature: Appmeasurement Implementation
role: Admin, Developer
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 199
ht-degree: 0%

---

# customerPerspective

A variável `customerPerspective` especifica se uma ocorrência de aplicativo móvel ocorreu enquanto o aplicativo estava em primeiro ou segundo plano. Ele é enviado para a coleta de dados da Adobe como o parâmetro de consulta `cp` e preenche a dimensão [Tipo de ocorrência](/help/components/dimensions/hit-type.md).

## Valores válidos

`customerPerspective` aceita os seguintes valores de cadeia de caracteres:

* `foreground`: A ocorrência ocorreu enquanto o aplicativo estava em uso ativo.
* `background`: A ocorrência ocorreu enquanto o aplicativo estava sendo executado em segundo plano, como uma atualização de local ou uma ocorrência acionada por uma notificação por push.

## Como essa variável é definida

O Adobe Mobile SDK (versão 4.13.6 e superior) define `customerPerspective` automaticamente; normalmente, você não o define manualmente. As ocorrências enviadas de um navegador por meio do AppMeasurement sempre se reportam como `foreground`. Se a variável não estiver presente em uma ocorrência, essa ocorrência será tratada como uma ocorrência em primeiro plano.

## Impacto nos relatórios

A distinção de primeiro/segundo plano afeta como as visitas são processadas:

* As visitas são contadas apenas quando contêm pelo menos uma ocorrência em primeiro plano.
* As ocorrências em segundo plano ainda podem ser atribuídas a eventos de conversão e podem ser analisadas por meio de [sessões com reconhecimento de contexto](/help/components/vrs/vrs-mobile-visit-processing.md) em conjuntos de relatórios virtuais. Esse comportamento é útil ao medir a eficácia das notificações por push.
