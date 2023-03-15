---
title: abort
description: A variável abort é um booleano que impede que uma ocorrência seja enviada para os servidores de coleta de dados da Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 48%

---

# abort

A variável `abort` é um booleano que pode impedir que a próxima chamada de rastreamento seja enviada para a Adobe. Uma funcionalidade semelhante existe no SDK da Web, permitindo retornar `false` antes do envio de um evento XDM.

## Cancelar o envio de um evento usando a extensão SDK da Web

Use o [!UICONTROL Ativado antes do retorno de chamada do envio do evento] editor de código e retorno `false`.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a [!UICONTROL Extensões] e clique na guia **[!UICONTROL Configurar]** botão em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Coleta de dados], clique no link **[!UICONTROL Editar no antes do envio do evento código de retorno de chamada]** botão.
1. No editor de código, coloque o seguinte código em qualquer condição que você deseje anular o envio de dados para o Edge:

```js
return false;
```

## Cancelar o envio de um evento implementando manualmente o SDK da Web

Use o `onBeforeEventSend` retorno de chamada e retorno `false`. Consulte [Modificação global de eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) na documentação do SDK da Web para obter mais informações.

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
>A variável `abort` é redefinida para `false` depois de cada chamada de rastreamento. Se precisar abortar chamadas de rastreamento subsequentes na mesma página, defina `abort` como `true` novamente.

Por exemplo, a variável `abort` pode ser definida na variável [`doPlugins()`](../functions/doplugins.md) que é a última função a ser executada antes que uma solicitação de imagem seja enviada para o Adobe. Este exemplo opera de forma semelhante ao `onBeforeEventSend` retorno de chamada usando o SDK da Web.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Centralize a lógica usada para identificar a atividade que você não deseja rastrear, como links personalizados ou links externos na exibição de anúncios.
