---
title: sa
description: Altere o conjunto de relatórios a qualquer momento em sua implementação.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 38%

---

# sa

O método `sa()` permite alterar dinamicamente e a qualquer momento um conjunto de relatórios na página. Se desejar enviar dados para conjuntos de relatórios diferentes sem um recarregamento de página, você pode usar esse método.

## Manuseio de conjuntos de relatórios usando o SDK da Web

O SDK da Web opera enviando dados para um conjunto de dados específico, que encaminha dados para os conjuntos de relatórios do Analytics desejados. Um único Armazenamento de dados pode encaminhar dados para vários Conjuntos de relatórios. Esta seção se aplica à extensão do SDK da Web e à implementação manual do SDK da Web.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique em **[!UICONTROL Datastreams]** à esquerda.
1. Clique no Armazenamento de dados desejado ou clique em **[!UICONTROL Novo fluxo de dados]**.
1. Clique em **[!UICONTROL Adicionar Serviço]**, em seguida selecione **[!UICONTROL Adobe Analytics]**.
1. Insira a ID do conjunto de relatórios desejada. Se desejar enviar os mesmos dados para vários conjuntos de relatórios, clique em **[!UICONTROL Adicionar conjunto de relatórios]**.
1. Depois que todos os conjuntos de relatórios desejados forem inseridos, clique em **[!UICONTROL Salvar]**.

## Definir o conjunto de dados desejado usando a extensão SDK da Web

A extensão Web SDK fornece uma lista suspensa Datastream para cada ambiente. Como alternativa, você pode inserir manualmente a ID do conjunto de dados.

1. Faça logon em [Coleta de dados do Adobe Experience Platform](https://experience.adobe.com/data-collection) usando suas credenciais da Adobe ID.
1. Clique na propriedade de tag desejada.
1. Vá para o [!UICONTROL Extensões] e clique no botão **[!UICONTROL Configurar]** botão abaixo [!UICONTROL Adobe Experience Platform Web SDK].
1. Em [!UICONTROL Datastreams], escolha o Datastream desejado na lista suspensa para cada ambiente.
1. Clique em **[!UICONTROL Salvar]**.

## Defina o conjunto de dados desejado manualmente implementando o SDK da Web

Defina as `edgeConfigId` variável de configuração para a ID do conjunto de dados. A ID do conjunto de dados é encontrada à direita ao visualizar um conjunto de dados na Coleta de dados do Adobe Experience Platform.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Consulte [Configurar o SDK da Web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) na documentação do SDK da Web para obter mais informações.

## Alterar o conjunto de relatórios usando a extensão Adobe Analytics

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
