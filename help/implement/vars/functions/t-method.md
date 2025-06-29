---
title: t
description: Envie uma chamada de rastreamento de exibição de página para a Adobe.
feature: Appmeasurement Implementation
exl-id: c4f5b9e2-57a3-4d89-8378-39b7a4737afc
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 56%

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
https://data.example.com/b/ss/examplersid/1/?v1=Example%20dimension%20item
```

A Adobe recebe a solicitação de imagem e analisa o cabeçalho da solicitação, o URL e os parâmetros da string de consulta. Os servidores de coleta de dados retornam uma imagem transparente com 1x1 pixels, exibida de maneira invisível em seu site.

## Enviar evento usando a extensão Web SDK

Use uma Ação para configurar o envio de dados do evento XDM para o Adobe. A sequência de dados recebe esses dados, aplica os mapeamentos configurados e encaminha esses dados para a Adobe Analytics se for um serviço adicionado a essa sequência de dados.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/br/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Ações], clique na Ação desejada ou clique no ícone **&#39;+&#39;** para adicionar uma ação.
1. Defina a lista suspensa [!UICONTROL Extensão] como **[!UICONTROL Adobe Experience Platform Web SDK]** e o [!UICONTROL Tipo de Ação] como **[!UICONTROL Enviar evento]**.

## Enviar evento implementando manualmente o Web SDK

Use o comando `sendEvent` para enviar dados ao Adobe. A sequência de dados recebe esses dados, aplica os mapeamentos configurados e encaminha esses dados para a Adobe Analytics se for um serviço adicionado a essa sequência de dados.

```js
alloy("sendEvent", {
  "xdm": {}
});
```

Consulte [`sendEvent`](https://experienceleague.adobe.com/pt-br/docs/experience-platform/web-sdk/commands/sendevent/overview) na documentação do Web SDK para obter mais informações.

## Chamada de rastreamento de exibição de página usando a extensão do Adobe Analytics

A extensão do Adobe Analytics na Coleção de dados da Adobe Experience Platform tem um local dedicado definido para uma chamada de rastreamento de exibição de página.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá até a guia [!UICONTROL Regras] e clique na regra desejada (ou crie uma regra).
1. Em [!UICONTROL Ações], clique na ação desejada ou clique no ícone **&#39;+&#39;** para adicionar uma ação.
1. Defina a lista suspensa [!UICONTROL Extensão] como **[!UICONTROL Adobe Analytics]** e o [!UICONTROL Tipo de Ação] como **[!UICONTROL Enviar Beacon]**.
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
