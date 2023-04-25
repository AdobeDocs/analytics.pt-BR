---
title: t
description: Envie uma chamada de rastreamento de exibição de página para a Adobe.
feature: Variables
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 57%

---

# t()

O método `t()` é um componente principal importante do Adobe Analytics. Ele captura todas as variáveis do Analytics definidas na página, compila em uma solicitação de imagem e envia esses dados para os servidores de coleta de dados da Adobe.

Por exemplo, considere o seguinte código JavaScript:

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Define config variables and page variables
s.trackingServerSecure = "data.example.com";
s.eVar1 = "Example dimension item";

// Compile the variables on the page into an image request to Adobe
s.t();
```

A execução do método `t()` utiliza todas as variáveis do Analytics definidas e formula um URL com base nessas variáveis. Algumas variáveis do Analytics determinam o URL da imagem, enquanto outras determinam os valores de parâmetro da string de consulta.

```text
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20value
```

A Adobe recebe a solicitação de imagem e analisa o cabeçalho da solicitação, o URL e os parâmetros da string de consulta. Os servidores de coleta de dados retornam uma imagem transparente com 1x1 pixels, exibida de maneira invisível em seu site.

## Enviar evento usando a extensão SDK da Web

Use uma Ação para configurar o envio de dados de evento XDM para o Adobe. O Datastream recebe esses dados, aplica os mapeamentos configurados e encaminha esses dados para o Adobe Analytics se for um serviço adicionado a esse Datastream.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Ações], clique na Ação desejada ou clique no botão **&#39;+&#39;** para adicionar uma ação.
1. Defina as [!UICONTROL Extensão] lista suspensa para **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Tipo de ação] para **[!UICONTROL Enviar evento]**.

## Enviar evento implementando manualmente o SDK da Web

Use o `sendEvent` para enviar dados ao Adobe. O Datastream recebe esses dados, aplica os mapeamentos configurados e encaminha esses dados para o Adobe Analytics se for um serviço adicionado a esse Datastream.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Consulte [Rastrear eventos](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=pt-BR) na documentação do SDK da Web para obter mais informações.

## Chamada de rastreamento de visualização de página usando a extensão Adobe Analytics

A extensão Adobe Analytics na Coleta de dados do Adobe Experience Platform tem um local dedicado definido para uma chamada de rastreamento de exibição de página.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Ações], clique na ação desejada ou clique no botão **&#39;+&#39;** para adicionar uma ação.
1. Defina as [!UICONTROL Extensão] lista suspensa para **[!UICONTROL Adobe Analytics]** e o [!UICONTROL Tipo de ação] para **[!UICONTROL Enviar beacon]**.
1. Clique no botão de opção `s.t()`.

## Método s.t() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.t()` quando quiser enviar uma chamada de rastreamento para a Adobe.

```js
s.t();
```

Como opção, você pode usar um objeto como argumento para substituir valores de variáveis. Consulte [substituições de variáveis](../../js/overrides.md) para obter mais informações.

```js
var y = new Object();
y.eVar1 = "Override value";
s.t(y);
```

>[!NOTE]
>
>As versões anteriores do AppMeasurement usavam várias linhas de código para chamar essa função. O código adicional historicamente acomodava soluções alternativas para navegadores diferentes. A padronização e as práticas recomendadas dos navegadores modernos não exigem mais esse bloco de código. Somente a chamada do método `s.t()` é necessária agora.
