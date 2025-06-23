---
title: abort
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 39%

---

# abort

A variável `abort` é um booliano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe. Uma funcionalidade semelhante existe no Web SDK, permitindo que você retorne `false` antes que um evento XDM seja enviado.

## Cancelar o envio de um evento usando a extensão do Web SDK

Use o [!UICONTROL Ligado antes de o evento enviar o editor de código de retorno de chamada] e retornar `false`.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleção de dados], clique no botão **[!UICONTROL Editar em antes de enviar o código de retorno de chamada]**.
1. No editor de códigos, coloque o seguinte código sob qualquer condição que você deseje anular o envio de dados para o Edge:

```js
return false;
```

## Cancelar o envio de um evento implementando manualmente o Web SDK

Use o retorno de chamada `onBeforeEventSend` e retorne `false`. Consulte [Modificando eventos globalmente](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do Web SDK para obter mais informações.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Uso da variável abort na extensão do Adobe Analytics

Não há um campo dedicado na extensão do Adobe Analytics para o uso dessa variável. Use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.abort no AppMeasurement e no editor de código personalizado da extensão do Analytics

A variável `s.abort` é booleana. O valor padrão é `false`.

* Se definida como `true`, a próxima chamada de rastreamento ([`t()`](../functions/t-method.md) ou [`tl()`](../functions/tl-method.md)) não enviará dados para a Adobe.
* Se definida como `false` ou não definida, essa variável não fará nada.

```js
s.abort = true;
```

>[!NOTE]
>
>A variável `abort` é redefinida para `false` depois de cada chamada de rastreamento. Se quiser anular chamadas de rastreamento subsequentes na mesma página, defina `abort` como `true` novamente.

A variável `abort` pode ser definida na função [`doPlugins()`](../functions/doplugins.md), que é a última a ser executada antes que uma solicitação de imagem seja enviada para o Adobe. Este exemplo opera de forma semelhante ao retorno de chamada `onBeforeEventSend` usando o Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.
