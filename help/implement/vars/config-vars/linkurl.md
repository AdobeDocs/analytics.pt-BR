---
title: linkURL
description: Substitua o URL de link gerado automaticamente que o AppMeasurement usa nas chamadas de rastreamento de link.
feature: Appmeasurement Implementation
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
role: Admin, Developer
source-git-commit: 7176e068dd05c5589d741f3194d2ad5d795e017d
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 37%

---

# linkURL

Sempre que uma chamada de rastreamento de link é enviada para o Adobe, o AppMeasurement detecta o URL que foi clicado. Este URL ajuda a determinar o tipo de link, como links de download e links de saída. Use a variável `linkURL` para substituir o URL detectado.

Não há dimensões no Analysis Workspace que relatem essa variável. Ele preenche a coluna `page_event_var1` em [Feeds de dados](/help/export/analytics-data-feed/data-feed-overview.md). Se você deseja rastrear o URL de um link clicado, a Adobe recomenda usar uma variável personalizada, como uma [Prop](../page-vars/prop.md).

## Vincular URL usando o Web SDK

O URL do link é mapeado para as seguintes variáveis:

* [objeto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `web.webInteraction.URL`
* [Objeto de dados](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.linkURL` ou `data.__adobe.analytics.pev1`

## Vincular URL usando a extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.linkURL no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.linkURL` é uma cadeia de caracteres, que contém a URL completa do link clicado. Essa variável não preenche nenhuma dimensão disponível no relatório.

```js
s.linkURL = "https://example.com";
```

Se o terceiro argumento do método [tl()](../functions/tl-method.md) não estiver definido, a variável `linkURL` será usada.
