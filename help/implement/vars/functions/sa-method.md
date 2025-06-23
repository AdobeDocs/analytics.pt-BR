---
title: sa
description: Altere o conjunto de relatórios a qualquer momento em sua implementação.
feature: Appmeasurement Implementation
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 42%

---

# sa

O método `sa()` permite alterar dinamicamente e a qualquer momento um conjunto de relatórios na página. Se desejar enviar dados para conjuntos de relatórios diferentes sem um recarregamento de página, você pode usar esse método.

## Lidar com conjuntos de relatórios usando o Web SDK

O Web SDK opera enviando dados para um fluxo de dados específico, que encaminha dados para o(s) conjunto(s) de relatórios desejado(s) do Analytics. Um único fluxo de dados pode encaminhar dados para vários conjuntos de relatórios. Esta seção se aplica à extensão Web SDK e à implementação manual do Web SDK.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Datastreams]** à esquerda.
1. Clique na sequência de dados desejada ou clique em **[!UICONTROL Nova sequência de dados]**.
1. Clique em **[!UICONTROL Adicionar Serviço]** e selecione **[!UICONTROL Adobe Analytics]**.
1. Insira a ID do conjunto de relatórios desejada. Se desejar enviar os mesmos dados para vários conjuntos de relatórios, clique em **[!UICONTROL Adicionar Conjunto de Relatórios]**.
1. Após inserir todos os conjuntos de relatórios desejados, clique em **[!UICONTROL Salvar]**.

## Defina a sequência de dados desejada usando a extensão Web SDK

A extensão Web SDK fornece uma lista suspensa de sequência de dados para cada ambiente. Como alternativa, você pode inserir manualmente a ID do fluxo de dados.

1. Faça logon na [Coleção de dados da Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para a guia [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** em [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Datastreams], escolha a Datastream desejada na lista suspensa para cada ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Defina o fluxo de dados desejado implementando manualmente o Web SDK

Defina a variável de configuração `datastreamId` para a ID de fluxo de dados. A ID da sequência de dados é encontrada à direita ao visualizar uma sequência de dados em Coleção de dados da Adobe Experience Platform.

```js
alloy("configure", {
  datastreamId: "example-a01f-4458-8cec-ef61de241c93",
  orgId: "ADB3LETTERSANDNUMBERS@AdobeOrg"
});
```

Consulte [Configurar o Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) na documentação do Web SDK para obter mais informações.

## Alterar conjunto de relatórios usando a extensão do Adobe Analytics

Não há uma maneira flexível de alterar o conjunto de relatórios na interface. É possível definir o conjunto de relatórios na opção [!UICONTROL Gerenciamento de biblioteca] ao configurar a extensão do Adobe Analytics. No entanto, não é possível alterar ou atualizar o conjunto de relatórios usando regras. Se desejar atualizar os valores do conjunto de relatórios depois de definidos, use o editor de código personalizado após a sintaxe do AppMeasurement.

## s.sa() no AppMeasurement e no editor de código personalizado da extensão do Analytics

Chame o método `s.sa()` para alterar o conjunto de relatórios de destino. Seu único argumento é uma string contendo uma ID de conjunto de relatórios ou várias IDs de conjuntos de relatórios delimitadas por uma vírgula. O argumento ID de conjunto de relatórios é obrigatório. Não use espaços no argumento em string.

```js
s.sa("examplersid");
```

Por exemplo, você pode alterar o conjunto de relatórios se o usuário executar uma ação específica em seu site.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
